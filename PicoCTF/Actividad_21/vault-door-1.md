## Objetivo
This vault uses some complicated arrays! I hope you can make sense of it, special agent. The source code for this vault is here: [VaultDoor1.java](https://jupiter.challenges.picoctf.org/static/ff2585f7afd21b81f69d2fbe37c081ae/VaultDoor1.java)
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act21/vaultdoor1$ wget https://jupiter.challenges.picoctf.org/static/ff2585f7afd21b81f69d2fbe37c0  
81ae/VaultDoor1.java  
--2024-10-28 10:30:47--  https://jupiter.challenges.picoctf.org/static/ff2585f7afd21b81f69d2fbe37c081ae/VaultDoor1.java  
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8  
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 2264 (2,2K) [application/octet-stream]  
Grabando a: «VaultDoor1.java»  
  
VaultDoor1.java                  100%[========================================================>]   2,21K  --.-KB/s    en 0s         
  
2024-10-28 10:30:55 (31,7 MB/s) - «VaultDoor1.java» guardado [2264/2264]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act21/vaultdoor1$ cat VaultDoor1.java    
import java.util.*;  
  
class VaultDoor1 {  
   public static void main(String args[]) {  
       VaultDoor1 vaultDoor = new VaultDoor1();  
       Scanner scanner = new Scanner(System.in);  
       System.out.print("Enter vault password: ");  
       String userInput = scanner.next();  
       String input = userInput.substring("picoCTF{".length(),userInput.length()-1);  
       if (vaultDoor.checkPassword(input)) {  
           System.out.println("Access granted.");  
       } else {  
           System.out.println("Access denied!");  
       }  
   }  
  
   // I came up with a more secure way to check the password without putting  
   // the password itself in the source code. I think this is going to be  
   // UNHACKABLE!! I hope Dr. Evil agrees...  
   //  
   // -Minion #8728  
   public boolean checkPassword(String password) {  
       return password.length() == 32 &&  
              password.charAt(0)  == 'd' &&  
              password.charAt(29) == '9' &&  
              password.charAt(4)  == 'r' &&  
              password.charAt(2)  == '5' &&  
              password.charAt(23) == 'r' &&  
              password.charAt(3)  == 'c' &&  
              password.charAt(17) == '4' &&  
              password.charAt(1)  == '3' &&  
              password.charAt(7)  == 'b' &&  
              password.charAt(10) == '_' &&  
              password.charAt(5)  == '4' &&  
              password.charAt(9)  == '3' &&  
              password.charAt(11) == 't' &&  
              password.charAt(15) == 'c' &&  
              password.charAt(8)  == 'l' &&  
              password.charAt(12) == 'H' &&  
              password.charAt(20) == 'c' &&  
              password.charAt(14) == '_' &&  
              password.charAt(6)  == 'm' &&  
              password.charAt(24) == '5' &&  
              password.charAt(18) == 'r' &&  
              password.charAt(13) == '3' &&  
              password.charAt(19) == '4' &&  
              password.charAt(21) == 'T' &&  
              password.charAt(16) == 'H' &&  
              password.charAt(27) == '5' &&  
              password.charAt(30) == '2' &&  
              password.charAt(25) == '_' &&  
              password.charAt(22) == '3' &&  
              password.charAt(28) == '0' &&  
              password.charAt(26) == '7' &&  
              password.charAt(31) == 'e';  
   }  
}
kali@KaliEND:~/Downloads/PicoCTF/Act21/vaultdoor1$ mousepad flag  
kali@KaliEND:~/Downloads/PicoCTF/Act21/vaultdoor1$ ls  
flag  VaultDoor1.java  
kali@KaliEND:~/Downloads/PicoCTF/Act21/vaultdoor1$ sort flag    
              password.charAt(0)  == 'd' &&  
              password.charAt(1)  == '3' &&  
              password.charAt(10) == '_' &&  
              password.charAt(11) == 't' &&  
              password.charAt(12) == 'H' &&  
              password.charAt(13) == '3' &&  
              password.charAt(14) == '_' &&  
              password.charAt(15) == 'c' &&  
              password.charAt(16) == 'H' &&  
              password.charAt(17) == '4' &&  
              password.charAt(18) == 'r' &&  
              password.charAt(19) == '4' &&  
              password.charAt(2)  == '5' &&  
              password.charAt(20) == 'c' &&  
              password.charAt(21) == 'T' &&  
              password.charAt(22) == '3' &&  
              password.charAt(23) == 'r' &&  
              password.charAt(24) == '5' &&  
              password.charAt(25) == '_' &&  
              password.charAt(26) == '7' &&  
              password.charAt(27) == '5' &&  
              password.charAt(28) == '0' &&  
              password.charAt(29) == '9' &&  
              password.charAt(3)  == 'c' &&  
              password.charAt(30) == '2' &&  
              password.charAt(31) == 'e';  
              password.charAt(4)  == 'r' &&  
              password.charAt(5)  == '4' &&  
              password.charAt(6)  == 'm' &&  
              password.charAt(7)  == 'b' &&  
              password.charAt(8)  == 'l' &&  
              password.charAt(9)  == '3' &&  
password.length() == 32 &&
kali@KaliEND:~/Downloads/PicoCTF/Act21/vaultdoor1$ nano flag    
kali@KaliEND:~/Downloads/PicoCTF/Act21/vaultdoor1$ cat flag | sort | awk '{print($3)}' | tr -d "'"  
d  
3  
5  
c  
r  
4  
m  
b  
l  
3  
_  
t  
H  
3  
_  
c  
H  
4  
r  
4  
c  
T  
3  
r  
5  
_  
7  
5  
0  
9  
2  
e
kali@KaliEND:~/Downloads/PicoCTF/Act21/vaultdoor1$ cat flag | sort | awk '{print($3)}' | tr -d "'" | tr -d "\n"  
d35cr4mbl3_tH3_cH4r4cT3r5_75092e
```
## Notas Adicionales
modificamos el archivo agregando 0 a los caracteres de un solo carácter para obtener los caracteres en orden y ajustar la flag:
`picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_75092e}`
### Referencias
## Objetivo
This vault uses for-loops and byte arrays. The source code for this vault is here: [VaultDoor3.java](https://jupiter.challenges.picoctf.org/static/a648ca6dd275b9454c5d0de6d0f6efd3/VaultDoor3.java)
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act21/vaultdoor3$ wget https://jupiter.challenges.picoctf.org/static/a648ca6dd275b9454c5d0de6d0f6  
efd3/VaultDoor3.java  
--2024-10-28 10:57:42--  https://jupiter.challenges.picoctf.org/static/a648ca6dd275b9454c5d0de6d0f6efd3/VaultDoor3.java  
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8  
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 1474 (1,4K) [application/octet-stream]  
Grabando a: «VaultDoor3.java»  
  
VaultDoor3.java                  100%[========================================================>]   1,44K  --.-KB/s    en 0s         
  
2024-10-28 10:57:46 (26,1 MB/s) - «VaultDoor3.java» guardado [1474/1474]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act21/vaultdoor3$ ls  
VaultDoor3.java  
kali@KaliEND:~/Downloads/PicoCTF/Act21/vaultdoor3$ cat VaultDoor3.java    
import java.util.*;  
  
class VaultDoor3 {  
   public static void main(String args[]) {  
       VaultDoor3 vaultDoor = new VaultDoor3();  
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
  
   // Our security monitoring team has noticed some intrusions on some of the  
   // less secure doors. Dr. Evil has asked me specifically to build a stronger  
   // vault door to protect his Doomsday plans. I just *know* this door will  
   // keep all of those nosy agents out of our business. Mwa ha!  
   //  
   // -Minion #2671  
   public boolean checkPassword(String password) {  
       if (password.length() != 32) {  
           return false;  
       }  
       char[] buffer = new char[32];  
       int i;  
       for (i=0; i<8; i++) {  
           buffer[i] = password.charAt(i);  
       }  
       for (; i<16; i++) {  
           buffer[i] = password.charAt(23-i);  
       }  
       for (; i<32; i+=2) {  
           buffer[i] = password.charAt(46-i);  
       }  
       for (i=31; i>=17; i-=2) {  
           buffer[i] = password.charAt(i);  
       }  
       String s = new String(buffer);  
       return s.equals("jU5t_a_sna_3lpm18gb41_u_4_mfr340");  
   }  
}
ali@KaliEND:~/Downloads/PicoCTF/Act21/vaultdoor3$ nano reverse.java    
kali@KaliEND:~/Downloads/PicoCTF/Act21/vaultdoor3$ javac reverse.java    
kali@KaliEND:~/Downloads/PicoCTF/Act21/vaultdoor3$ java reverse.java    
Password: picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_1fb380}  
kali@KaliEND:~/Downloads/PicoCTF/Act21/vaultdoor3$ cat reverse.java    
import java.util.*;  
  
class VaultDoor3 {  
   public static void main(String args[]) {  
       VaultDoor3 vaultDoor = new VaultDoor3();  
       String password = vaultDoor.findPassword();  
       System.out.println("Password: picoCTF{" + password + "}");  
   }  
  
   public String findPassword() {  
       String target = "jU5t_a_sna_3lpm18gb41_u_4_mfr340";  
       char[] password = new char[32];  
  
       for (int i = 0; i < 8; i++) {  
           password[i] = target.charAt(i);  
       }  
  
       for (int i = 8; i < 16; i++) {  
           password[23 - i] = target.charAt(i);  
       }  
  
       for (int i = 16; i < 32; i += 2) {  
           password[46 - i] = target.charAt(i);  
       }  
  
       for (int i = 31; i >= 17; i -= 2) {  
           password[i] = target.charAt(i);  
       }  
  
       return new String(password);  
   }  
  
   public boolean checkPassword(String password) {  
       if (password.length() != 32) {  
           return false;  
       }  
       char[] buffer = new char[32];  
       int i;  
       for (i=0; i<8; i++) {  
           buffer[i] = password.charAt(i);  
       }  
       for (; i<16; i++) {  
           buffer[i] = password.charAt(23-i);  
       }  
       for (; i<32; i+=2) {  
           buffer[i] = password.charAt(46-i);  
       }  
       for (i=31; i>=17; i-=2) {  
           buffer[i] = password.charAt(i);  
       }  
       String s = new String(buffer);  
       return s.equals("jU5t_a_sna_3lpm18gb41_u_4_mfr340");  
   }  
}  
kali@KaliEND:~/Downloads/PicoCTF/Act21/vaultdoor3$
```
## Notas Adicionales
Creamos y modificamos el .java para que funcionara al revez y obtener la flag que estaba en desorden.
`picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_1fb380}`
### Referencias
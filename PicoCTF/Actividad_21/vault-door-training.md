## Objetivo
Your mission is to enter Dr. Evil's laboratory and retrieve the blueprints for his Doomsday Project. The laboratory is protected by a series of locked vault doors. Each door is controlled by a computer and requires a password to open. Unfortunately, our undercover agents have not been able to obtain the secret passwords for the vault doors, but one of our junior agents obtained the source code for each vault's computer! You will need to read the source code for each level to figure out what the password is for that vault door. As a warmup, we have created a replica vault in our training facility. The source code for the training vault is here: [VaultDoorTraining.java](https://jupiter.challenges.picoctf.org/static/1afdf83322ee9c0040f8e3a3c047e18b/VaultDoorTraining.java)
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act21$ wget https://jupiter.challenges.picoctf.org/static/1afdf83322ee9c0040f8e3a3c047e18b/VaultD  
oorTraining.java  
--2024-10-28 10:17:28--  https://jupiter.challenges.picoctf.org/static/1afdf83322ee9c0040f8e3a3c047e18b/VaultDoorTraining.java  
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8  
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 943 [application/octet-stream]  
Grabando a: «VaultDoorTraining.java»  
  
VaultDoorTraining.java           100%[========================================================>]     943  --.-KB/s    en 0s         
  
2024-10-28 10:17:35 (14,4 MB/s) - «VaultDoorTraining.java» guardado [943/943]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act21$ ls  
VaultDoorTraining.java
kali@KaliEND:~/Downloads/PicoCTF/Act21$ java --version  
openjdk 23.0.1 2024-10-15  
OpenJDK Runtime Environment (build 23.0.1+11-Debian-1)  
OpenJDK 64-Bit Server VM (build 23.0.1+11-Debian-1, mixed mode, sharing)  
kali@KaliEND:~/Downloads/PicoCTF/Act21$ javac --version  
javac 21.0.5  
kali@KaliEND:~/Downloads/PicoCTF/Act21$ cat VaultDoorTraining.java    
import java.util.*;  
  
class VaultDoorTraining {  
   public static void main(String args[]) {  
       VaultDoorTraining vaultDoor = new VaultDoorTraining();  
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
  
   // The password is below. Is it safe to put the password in the source code?  
   // What if somebody stole our source code? Then they would know what our  
   // password is. Hmm... I will think of some ways to improve the security  
   // on the other doors.  
   //  
   // -Minion #9567  
   public boolean checkPassword(String password) {  
       return password.equals("w4rm1ng_Up_w1tH_jAv4_eec0716b713");  
   }  
}  
kali@KaliEND:~/Downloads/PicoCTF/Act21$ javac VaultDoorTraining.java    
kali@KaliEND:~/Downloads/PicoCTF/Act21$ ls  
VaultDoorTraining.class  VaultDoorTraining.java  
kali@KaliEND:~/Downloads/PicoCTF/Act21$ java VaultDoorTraining.  
Error: no se ha encontrado o cargado la clase principal VaultDoorTraining.  
Causado por: java.lang.ClassNotFoundException: VaultDoorTraining.  
kali@KaliEND:~/Downloads/PicoCTF/Act21$ java VaultDoorTraining.java    
Enter vault password: hola       
Exception in thread "main" java.lang.StringIndexOutOfBoundsException: Range [8, 3) out of bounds for length 4  
       at java.base/jdk.internal.util.Preconditions$1.apply(Preconditions.java:55)  
       at java.base/jdk.internal.util.Preconditions$1.apply(Preconditions.java:52)  
       at java.base/jdk.internal.util.Preconditions$4.apply(Preconditions.java:213)  
       at java.base/jdk.internal.util.Preconditions$4.apply(Preconditions.java:210)  
       at java.base/jdk.internal.util.Preconditions.outOfBounds(Preconditions.java:98)  
       at java.base/jdk.internal.util.Preconditions.outOfBoundsCheckFromToIndex(Preconditions.java:112)  
       at java.base/jdk.internal.util.Preconditions.checkFromToIndex(Preconditions.java:349)  
       at java.base/java.lang.String.checkBoundsBeginEnd(String.java:4963)  
       at java.base/java.lang.String.substring(String.java:2925)  
       at VaultDoorTraining.main(VaultDoorTraining.java:9)  
kali@KaliEND:~/Downloads/PicoCTF/Act21$ java VaultDoorTraining.java    
Enter vault password: picoCTF{w4rm1ng_Up_w1tH_jAv4_eec0716b713}  
Access granted.
```
## Notas Adicionales
flag:
`picoCTF{w4rm1ng_Up_w1tH_jAv4_eec0716b713}`
### Referencias
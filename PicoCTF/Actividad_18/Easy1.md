## Objetivo 
The one time pad can be cryptographically secure, but not when you know the key. Can you solve this? We've given you the encrypted flag, key, and a table to help `UFJKXQZQUNB` with the key of `SOLVECRYPTO`. Can you use this [table](https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt) to solve it?.
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act18$ wget https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.  
txt  
--2024-10-17 21:20:39--  https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt  
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8  
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 1571 (1,5K) [application/octet-stream]  
Grabando a: «table.txt»  
  
table.txt                        100%[========================================================>]   1,53K  --.-KB/s    en 0s         
  
2024-10-17 21:20:39 (26,6 MB/s) - «table.txt» guardado [1571/1571]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act18$ ls  
ciphertext  table.txt  the_numbers.png  
kali@KaliEND:~/Downloads/PicoCTF/Act18$ cat table.txt    
   A B C D E F G H I J K L M N O P Q R S T U V W X Y Z    
  +----------------------------------------------------  
A | A B C D E F G H I J K L M N O P Q R S T U V W X Y Z  
B | B C D E F G H I J K L M N O P Q R S T U V W X Y Z A  
C | C D E F G H I J K L M N O P Q R S T U V W X Y Z A B  
D | D E F G H I J K L M N O P Q R S T U V W X Y Z A B C  
E | E F G H I J K L M N O P Q R S T U V W X Y Z A B C D  
F | F G H I J K L M N O P Q R S T U V W X Y Z A B C D E  
G | G H I J K L M N O P Q R S T U V W X Y Z A B C D E F  
H | H I J K L M N O P Q R S T U V W X Y Z A B C D E F G  
I | I J K L M N O P Q R S T U V W X Y Z A B C D E F G H  
J | J K L M N O P Q R S T U V W X Y Z A B C D E F G H I  
K | K L M N O P Q R S T U V W X Y Z A B C D E F G H I J  
L | L M N O P Q R S T U V W X Y Z A B C D E F G H I J K  
M | M N O P Q R S T U V W X Y Z A B C D E F G H I J K L  
N | N O P Q R S T U V W X Y Z A B C D E F G H I J K L M  
O | O P Q R S T U V W X Y Z A B C D E F G H I J K L M N  
P | P Q R S T U V W X Y Z A B C D E F G H I J K L M N O  
Q | Q R S T U V W X Y Z A B C D E F G H I J K L M N O P  
R | R S T U V W X Y Z A B C D E F G H I J K L M N O P Q  
S | S T U V W X Y Z A B C D E F G H I J K L M N O P Q R  
T | T U V W X Y Z A B C D E F G H I J K L M N O P Q R S  
U | U V W X Y Z A B C D E F G H I J K L M N O P Q R S T  
V | V W X Y Z A B C D E F G H I J K L M N O P Q R S T U  
W | W X Y Z A B C D E F G H I J K L M N O P Q R S T U V  
X | X Y Z A B C D E F G H I J K L M N O P Q R S T U V W  
Y | Y Z A B C D E F G H I J K L M N O P Q R S T U V W X  
Z | Z A B C D E F G H I J K L M N O P Q R S T U V W X Y  
  
kali@KaliEND:~/Downloads/PicoCTF/Act18$
```
## Notas Adicionales 
en esto hay que hacer match entre las columnas y las filas del codigo usando la key `SOLVECRYPTO` y este texto que nos proporcionan `UFJKXQZQUNB`
y asi obtenemos: CRYPTOISFUN

flag: `picoCTF{CRYPTOISFUN}`
### Referencias
## Objetivo 
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/14/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/14/level2.flag.txt.enc) in the same directory too.

---
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/parte2$ wget https://artifacts.picoctf.net/c/14/level2.flag.txt.enc  
--2024-09-17 23:52:46--  https://artifacts.picoctf.net/c/14/level2.flag.txt.enc  
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:9a00:16:5ec5:2840:93a1, 2600:9000:25  
ed:2a00:16:5ec5:2840:93a1, 2600:9000:25ed:5e00:16:5ec5:2840:93a1, ...  
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:25ed:9a00:16:5ec5:2840:93a1|:443... conn  
ected.  
HTTP request sent, awaiting response... 200 OK  
Length: 31 [application/octet-stream]  
Saving to: ‘level2.flag.txt.enc’  
  
level2.flag.txt.enc         100%[=========================================>]      31  --.-KB/s    in 0s         
  
2024-09-17 23:52:46 (15.5 MB/s) - ‘level2.flag.txt.enc’ saved [31/31]  
  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ ls  
fixme1.py  fixme2.py  level1.flag.txt.enc  level1.py  level2.flag.txt.enc  level2.py  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ cat level2.py    
### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################  
def str_xor(secret, key):  
   #extend key to secret length  
   new_key = key  
   i = 0  
   while len(new_key) < len(secret):  
       new_key = new_key + key[i]  
       i = (i + 1) % len(key)           
   return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])  
###############################################################################  
  
flag_enc = open('level2.flag.txt.enc', 'rb').read()  
  
  
  
def level_2_pw_check():  
   user_pw = input("Please enter correct password for flag: ")  
   if( user_pw == chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39) ):  
       print("Welcome back... your flag, user:")  
       decryption = str_xor(flag_enc.decode(), user_pw)  
       print(decryption)  
       return  
   print("That password is incorrect")  
  
  
  
level_2_pw_check()  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ python3 level2.py    
Please enter correct password for flag: 4ec9  
Welcome back... your flag, user:  
picoCTF{tr45h_51ng1ng_9701e681}  
kali@KaliEND:~/Downloads/PicoCTF/parte2$
```
## Notas Adicionales 
casi lo mismo que el anterior pero ahora tenia la contraseña correcta ahora  oculta en formato hexadecimal en lugar de estar explícitamente escrita como un número.
picoCTF{tr45h_51ng1ng_9701e681}
### Referencias
cyberchef

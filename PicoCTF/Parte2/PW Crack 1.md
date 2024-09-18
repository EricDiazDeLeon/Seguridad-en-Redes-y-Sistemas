## Objetivo 
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/12/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/12/level1.flag.txt.enc) in the same directory too.
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/parte2$ wget https://artifacts.picoctf.net/c/12/level1.py  
--2024-09-17 23:49:27--  https://artifacts.picoctf.net/c/12/level1.py  
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:9400:16:5ec5:2840:93a1, 2600:9000:25  
ed:1e00:16:5ec5:2840:93a1, 2600:9000:25ed:3e00:16:5ec5:2840:93a1, ...  
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:25ed:9400:16:5ec5:2840:93a1|:443... conn  
ected.  
HTTP request sent, awaiting response... 200 OK  
Length: 876 [application/octet-stream]  
Saving to: ‘level1.py’  
  
level1.py                   100%[=========================================>]     876  --.-KB/s    in 0s         
  
2024-09-17 23:49:28 (10.2 MB/s) - ‘level1.py’ saved [876/876]  
  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ ls  
fixme1.py  fixme2.py  level1.flag.txt.enc  level1.py  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ python3 level1.py    
Please enter correct password for flag: nose  
That password is incorrect  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ cat level1.py    
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
  
  
flag_enc = open('level1.flag.txt.enc', 'rb').read()  
  
  
  
def level_1_pw_check():  
   user_pw = input("Please enter correct password for flag: ")  
   if( user_pw == "8713"):  
       print("Welcome back... your flag, user:")  
       decryption = str_xor(flag_enc.decode(), user_pw)  
       print(decryption)  
       return  
   print("That password is incorrect")  
  
  
  
level_1_pw_check()  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ python3 level1.py    
Please enter correct password for flag: 8713  
Welcome back... your flag, user:  
picoCTF{545h_r1ng1ng_1b2fd683}  
kali@KaliEND:~/Downloads/PicoCTF/parte2$
```
## Notas Adicionales 
la contrasena estaba dentro del codigo del archivo solo fue cuestion de darle un cat, buscarla y despues correr el programa con python.
picoCTF{545h_r1ng1ng_1b2fd683}
### Referencias


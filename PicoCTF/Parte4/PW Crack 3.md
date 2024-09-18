## Objetivo 
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/18/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/18/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/18/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/parte4$ wget https://artifacts.picoctf.net/c/18/level3.py  
--2024-09-17 16:15:05--  https://artifacts.picoctf.net/c/18/level3.py  
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:f800:16:5ec5:2840:93a1, 2600:9000:25  
ed:3800:16:5ec5:2840:93a1, 2600:9000:25ed:5800:16:5ec5:2840:93a1, ...  
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:25ed:f800:16:5ec5:2840:93a1|:443... conn  
ected.  
HTTP request sent, awaiting response... 200 OK  
Length: 1337 (1.3K) [application/octet-stream]  
Saving to: ‘level3.py’  
  
level3.py                   100%[=========================================>]   1.31K  --.-KB/s    in 0s         
  
2024-09-17 16:15:05 (19.2 MB/s) - ‘level3.py’ saved [1337/1337]  
  
kali@KaliEND:~/Downloads/PicoCTF/parte4$ wget https://artifacts.picoctf.net/c/18/level3.flag.txt.enc  
--2024-09-17 16:15:19--  https://artifacts.picoctf.net/c/18/level3.flag.txt.enc  
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:1a00:16:5ec5:2840:93a1, 2600:9000:25  
ed:f800:16:5ec5:2840:93a1, 2600:9000:25ed:3800:16:5ec5:2840:93a1, ...  
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:25ed:1a00:16:5ec5:2840:93a1|:443... conn  
ected.  
HTTP request sent, awaiting response... 200 OK  
Length: 31 [application/octet-stream]  
Saving to: ‘level3.flag.txt.enc’  
  
level3.flag.txt.enc         100%[=========================================>]      31  --.-KB/s    in 0s         
  
2024-09-17 16:15:19 (22.8 MB/s) - ‘level3.flag.txt.enc’ saved [31/31]  
  
kali@KaliEND:~/Downloads/PicoCTF/parte4$ wget https://artifacts.picoctf.net/c/18/level3.hash.bin  
--2024-09-17 16:15:33--  https://artifacts.picoctf.net/c/18/level3.hash.bin  
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:4000:16:5ec5:2840:93a1, 2600:9000:25  
ed:1a00:16:5ec5:2840:93a1, 2600:9000:25ed:f800:16:5ec5:2840:93a1, ...  
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:25ed:4000:16:5ec5:2840:93a1|:443... conn  
ected.  
HTTP request sent, awaiting response... 200 OK  
Length: 16 [application/octet-stream]  
Saving to: ‘level3.hash.bin’  
  
level3.hash.bin             100%[=========================================>]      16  --.-KB/s    in 0s         
  
2024-09-17 16:15:33 (10.3 MB/s) - ‘level3.hash.bin’ saved [16/16]  
  
kali@KaliEND:~/Downloads/PicoCTF/parte4$ ls  
level3.flag.txt.enc  level3.hash.bin  level3.py  
kali@KaliEND:~/Downloads/PicoCTF/parte4$ python level3.py    
bash: python: command not found  
kali@KaliEND:~/Downloads/PicoCTF/parte4$ python3 level3.py    
Please enter correct password for flag: ksdl  
That password is incorrect  
kali@KaliEND:~/Downloads/PicoCTF/parte4$ cat level3.py  
import hashlib  
  
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
  
flag_enc = open('level3.flag.txt.enc', 'rb').read()  
correct_pw_hash = open('level3.hash.bin', 'rb').read()  
  
  
def hash_pw(pw_str):  
   pw_bytes = bytearray()  
   pw_bytes.extend(pw_str.encode())  
   m = hashlib.md5()  
   m.update(pw_bytes)  
   return m.digest()  
  
  
def level_3_pw_check():  
   user_pw = input("Please enter correct password for flag: ")  
   user_pw_hash = hash_pw(user_pw)  
      
   if( user_pw_hash == correct_pw_hash ):  
       print("Welcome back... your flag, user:")  
       decryption = str_xor(flag_enc.decode(), user_pw)  
       print(decryption)  
       return  
   print("That password is incorrect")  
  
  
  
level_3_pw_check()  
  
  
# The strings below are 7 possibilities for the correct password.    
#   (Only 1 is correct)  
pos_pw_list = ["8799", "d3ab", "1ea2", "acaf", "2295", "a9de", "6f3d"]  
  
kali@KaliEND:~/Downloads/PicoCTF/parte4$ python3 level3.py    
Please enter correct password for flag: 8799  
That password is incorrect  
kali@KaliEND:~/Downloads/PicoCTF/parte4$ python3 level3.py    
Please enter correct password for flag: 1ea2  
That password is incorrect  
kali@KaliEND:~/Downloads/PicoCTF/parte4$ python3 level3.py    
Please enter correct password for flag: 2295  
Welcome back... your flag, user:  
picoCTF{m45h_fl1ng1ng_6f98a49f}
```
## Notas Adicionales 
ejecutamos el programa usando python, este requiere una contraseña la cual no tenemos, pero si le hacemos un cat al programa aparte de ver su funcionamiento interno podemos ver que hay dentro del codigo algunas posibles contraseñas, de las cuales una es la correcta.
### Referencias

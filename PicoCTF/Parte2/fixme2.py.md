## Objetivo 
Fix the syntax error in the Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/6/fixme2.py)
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/parte2$ wget https://artifacts.picoctf.net/c/6/fixme2.py  
--2024-09-17 23:29:39--  https://artifacts.picoctf.net/c/6/fixme2.py  
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:c00:16:5ec5:2840:93a1, 2600:9000:25e  
d:d800:16:5ec5:2840:93a1, 2600:9000:25ed:8a00:16:5ec5:2840:93a1, ...  
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:25ed:c00:16:5ec5:2840:93a1|:443... conne  
cted.  
HTTP request sent, awaiting response... 200 OK  
Length: 1029 (1.0K) [application/octet-stream]  
Saving to: ‘fixme2.py’  
  
fixme2.py                   100%[=========================================>]   1.00K  --.-KB/s    in 0s         
  
2024-09-17 23:29:40 (43.4 MB/s) - ‘fixme2.py’ saved [1029/1029]  
  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ ls  
fixme1.py  fixme2.py  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ cat fixme2.py    
  
import random  
  
  
  
def str_xor(secret, key):  
   #extend key to secret length  
   new_key = key  
   i = 0  
   while len(new_key) < len(secret):  
       new_key = new_key + key[i]  
       i = (i + 1) % len(key)           
   return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])  
  
  
flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr  
(0x58) + chr(0x18) + chr(0x11) + chr(0x41) + chr(0x09) + chr(0x5f) + chr(0x1f) + chr(0x10) + chr(0x3b) + chr(0  
x1b) + chr(0x55) + chr(0x1a) + chr(0x34) + chr(0x5d) + chr(0x51) + chr(0x40) + chr(0x54) + chr(0x09) + chr(0x0  
5) + chr(0x04) + chr(0x57) + chr(0x1b) + chr(0x11) + chr(0x31) + chr(0x0d) + chr(0x5f) + chr(0x05) + chr(0x40)  
+ chr(0x04) + chr(0x0b) + chr(0x0d) + chr(0x0a) + chr(0x19)  
  
    
flag = str_xor(flag_enc, 'enkidu')  
  
# Check that flag is not empty  
if flag = "":  
 print('String XOR encountered a problem, quitting.')  
else:  
 print('That is correct! Here\'s your flag: ' + flag)  
  
  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ python3 fixme2.py    
 File "/home/kali/Downloads/PicoCTF/parte2/fixme2.py", line 22  
   if flag = "":  
      ^^^^^^^^^  
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ nano fixme2.py    
kali@KaliEND:~/Downloads/PicoCTF/parte2$ python3 fixme2.py    
 File "/home/kali/Downloads/PicoCTF/parte2/fixme2.py", line 20  
   if flag = "":  
      ^^^^^^^^^  
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ nano fixme2.py    
kali@KaliEND:~/Downloads/PicoCTF/parte2$ python3 fixme2.py    
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_f6a5aefc}  
kali@KaliEND:~/Downloads/PicoCTF/parte2$
```
## Notas Adicionales 
otra ves era modificar un archivo .py para arreglar la sintaxis.
### Referencias


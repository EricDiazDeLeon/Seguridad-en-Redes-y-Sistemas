## Objetivo 
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/a14be2648c73e3cda5fc8490a2f476af/warm) has extraordinarily helpful information...
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/parte3$ wget https://mercury.picoctf.net/static/a14be2648c73e3cda5fc8490a2f47  
6af/warm  
--2024-09-17 14:36:23--  https://mercury.picoctf.net/static/a14be2648c73e3cda5fc8490a2f476af/warm  
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142  
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.  
HTTP request sent, awaiting response... 200 OK  
Length: 10936 (11K) [application/octet-stream]  
Saving to: ‘warm’  
  
warm                        100%[=========================================>]  10.68K  --.-KB/s    in 0s         
  
2024-09-17 14:36:23 (145 MB/s) - ‘warm’ saved [10936/10936]  
  
kali@KaliEND:~/Downloads/PicoCTF/parte3$ ls  
file  flag  static  warm  
kali@KaliEND:~/Downloads/PicoCTF/parte3$ file warn  
warn: cannot open `warn' (No such file or directory)  
kali@KaliEND:~/Downloads/PicoCTF/parte3$ file warm  
warm: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux  
-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=3181a501366281ab5eba1c41e54a1f40800e3966, with debug_info, no  
t stripped  
kali@KaliEND:~/Downloads/PicoCTF/parte3$ chmod 777 warm  
kali@KaliEND:~/Downloads/PicoCTF/parte3$ ls  
file  flag  static  warm  
kali@KaliEND:~/Downloads/PicoCTF/parte3$ ./warm  
Hello user! Pass me a -h to learn what I can do!  
kali@KaliEND:~/Downloads/PicoCTF/parte3$ ./warm -h  
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_755f3544}  
kali@KaliEND:~/Downloads/PicoCTF/parte3$
```
## Notas Adicionales 

### Referencias


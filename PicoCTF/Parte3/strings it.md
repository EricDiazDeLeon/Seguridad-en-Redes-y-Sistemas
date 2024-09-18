## Objetivo 
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/5bd86036f013ac3b9c958499adf3e2e2/strings) without running it?
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/parte3$ wget https://jupiter.challenges.picoctf.org/static/5bd86036f013ac3b9c  
958499adf3e2e2/strings  
--2024-09-17 14:38:40--  https://jupiter.challenges.picoctf.org/static/5bd86036f013ac3b9c958499adf3e2e2/string  
s  
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8  
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.  
HTTP request sent, awaiting response... 200 OK  
Length: 776032 (758K) [application/octet-stream]  
Saving to: ‘strings’  
  
strings                     100%[=========================================>] 757.84K   704KB/s    in 1.1s       
  
2024-09-17 14:38:43 (704 KB/s) - ‘strings’ saved [776032/776032]  
  
kali@KaliEND:~/Downloads/PicoCTF/parte3$ ls  
file  flag  static  strings  warm  
kali@KaliEND:~/Downloads/PicoCTF/parte3$ file strings    
strings: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-li  
nux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=047a5079a5f563cd0e540d28f42a37161093ffda, not stripped  
kali@KaliEND:~/Downloads/PicoCTF/parte3$ strings -n 15 strings| grep picoCTF  
picoCTF{5tRIng5_1T_827aee91}  
```
## Notas Adicionales 

### Referencias


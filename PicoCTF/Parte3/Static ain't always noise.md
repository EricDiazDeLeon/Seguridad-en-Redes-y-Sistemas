## Objetivo 
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/static)? This [BASH script](https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/ltdis.sh) might help!
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/parte3$ wget https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672  
dbd/static  
--2024-09-17 14:28:52--  https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/static  
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142  
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.  
HTTP request sent, awaiting response... 200 OK  
Length: 8376 (8.2K) [application/octet-stream]  
Saving to: ‘static’  
  
static                      100%[=========================================>]   8.18K  --.-KB/s    in 0s         
  
2024-09-17 14:28:52 (127 MB/s) - ‘static’ saved [8376/8376]  
  
kali@KaliEND:~/Downloads/PicoCTF/parte3$ ls  
file  flag  static  
kali@KaliEND:~/Downloads/PicoCTF/parte3$ chmod 777 static    
kali@KaliEND:~/Downloads/PicoCTF/parte3$ ./static    
Oh hai! Wait what? A flag? Yes, its around here somewhere!  
kali@KaliEND:~/Downloads/PicoCTF/parte3$ ls  
file  flag  static  
kali@KaliEND:~/Downloads/PicoCTF/parte3$ strings static | grep picoCTF  
picoCTF{d15a5m_t34s3r_1e6a7731}
```
## Notas Adicionales 

### Referencias


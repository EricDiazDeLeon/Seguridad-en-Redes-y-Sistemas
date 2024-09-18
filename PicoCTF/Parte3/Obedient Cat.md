## Objetivo 
This file has a flag in plain sight (aka "in-the-clear").
## Solución  
```bash
ali@KaliEND:~/Downloads/PicoCTF/parte3$ wget https://mercury.picoctf.net/static/217686fc11d733b80be62dcfcfca6  
c75/flag  
--2024-09-17 14:19:53--  https://mercury.picoctf.net/static/217686fc11d733b80be62dcfcfca6c75/flag  
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142  
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.  
HTTP request sent, awaiting response... 200 OK  
Length: 34 [application/octet-stream]  
Saving to: ‘flag’  
  
flag                        100%[=========================================>]      34  --.-KB/s    in 0s         
  
2024-09-17 14:19:54 (17.2 MB/s) - ‘flag’ saved [34/34]  
  
kali@KaliEND:~/Downloads/PicoCTF/parte3$ ls  
file  flag  
kali@KaliEND:~/Downloads/PicoCTF/parte3$ cat flag    
picoCTF{s4n1ty_v3r1f13d_b5aeb3dd}
```
## Notas Adicionales 
Solo le hicimos un cat al archivo para ver su contenido.
picoCTF{s4n1ty_v3r1f13d_b5aeb3dd}
### Referencias


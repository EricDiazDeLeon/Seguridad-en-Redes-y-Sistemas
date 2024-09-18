## Objetivo 
Run the Python script and convert the given number from decimal to binary to get the flag.[Download Python script](https://artifacts.picoctf.net/c/23/convertme.py)
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/parte2$ wget https://artifacts.picoctf.net/c/23/convertme.py  
--2024-09-17 23:16:42--  https://artifacts.picoctf.net/c/23/convertme.py  
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:6800:16:5ec5:2840:93a1, 2600:9000:25  
ed:5400:16:5ec5:2840:93a1, 2600:9000:25ed:1600:16:5ec5:2840:93a1, ...  
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:25ed:6800:16:5ec5:2840:93a1|:443... conn  
ected.  
HTTP request sent, awaiting response... 200 OK  
Length: 1189 (1.2K) [application/octet-stream]  
Saving to: ‘convertme.py’  
  
convertme.py                100%[=========================================>]   1.16K  --.-KB/s    in 0s         
  
2024-09-17 23:16:42 (45.0 MB/s) - ‘convertme.py’ saved [1189/1189]  
  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ ls  
code.py  codebook.txt  convertme.py  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ python3 convertme.py    
If 56 is in decimal base, what is it in binary base?  
Answer: das  
That isn't a binary number. Binary numbers contain only 1's and 0's  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ cat codebook.txt    
azbycxdwevfugthsirjqkplomn  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ python3 convertme.py    
If 27 is in decimal base, what is it in binary base?  
Answer: 10101  
21 and 27 are not equal.  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ me equivoque jaja lei mal  
bash: me: command not found  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ python3 convertme.py    
If 59 is in decimal base, what is it in binary base?  
Answer: 111011  
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_9c3b7d4d}  
kali@KaliEND:~/Downloads/PicoCTF/parte2$
```
## Notas Adicionales 
era ejecutar el archivo py y convertir un numero de decimal a binario.
### Referencias


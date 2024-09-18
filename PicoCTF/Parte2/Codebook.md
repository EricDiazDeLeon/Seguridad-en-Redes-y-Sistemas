## Objetivo 
Run the Python script `code.py` in the same directory as `codebook.txt`.

- [Download code.py](https://artifacts.picoctf.net/c/2/code.py)
- [Download codebook.txt](https://artifacts.picoctf.net/c/2/codebook.txt)
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/parte2$ wget https://artifacts.picoctf.net/c/2/code.py  
--2024-09-17 23:14:44--  https://artifacts.picoctf.net/c/2/code.py  
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:9600:16:5ec5:2840:93a1, 2600:9000:25  
ed:9c00:16:5ec5:2840:93a1, 2600:9000:25ed:4000:16:5ec5:2840:93a1, ...  
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:25ed:9600:16:5ec5:2840:93a1|:443... conn  
ected.  
HTTP request sent, awaiting response... 200 OK  
Length: 1278 (1.2K) [application/octet-stream]  
Saving to: ‘code.py’  
  
code.py                     100%[=========================================>]   1.25K  --.-KB/s    in 0s         
  
2024-09-17 23:14:45 (58.2 MB/s) - ‘code.py’ saved [1278/1278]  
  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ wget https://artifacts.picoctf.net/c/2/codebook.txt  
--2024-09-17 23:14:59--  https://artifacts.picoctf.net/c/2/codebook.txt  
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:ee00:16:5ec5:2840:93a1, 2600:9000:25  
ed:a400:16:5ec5:2840:93a1, 2600:9000:25ed:2200:16:5ec5:2840:93a1, ...  
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:25ed:ee00:16:5ec5:2840:93a1|:443... conn  
ected.  
HTTP request sent, awaiting response... 200 OK  
Length: 27 [application/octet-stream]  
Saving to: ‘codebook.txt’  
  
codebook.txt                100%[=========================================>]      27  --.-KB/s    in 0s         
  
2024-09-17 23:14:59 (524 KB/s) - ‘codebook.txt’ saved [27/27]  
  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ ls  
code.py  codebook.txt  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ python3 code.py    
picoCTF{c0d3b00k_455157_7d102d7a}  
kali@KaliEND:~/Downloads/PicoCTF/parte2$
```
## Notas Adicionales 
Solo era descargar los archivos y ejecutar el .py
### Referencias


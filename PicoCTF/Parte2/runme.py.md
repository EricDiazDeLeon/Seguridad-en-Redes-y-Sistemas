## Objetivo 
Run the `runme.py` script to get the flag. Download the script with your browser or with `wget` in the webshell.[Download runme.py Python script](https://artifacts.picoctf.net/c/34/runme.py)
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/parte2$ wget https://artifacts.picoctf.net/c/34/runme.py  
--2024-09-17 23:54:53--  https://artifacts.picoctf.net/c/34/runme.py  
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:9000:16:5ec5:2840:93a1, 2600:9000:25  
ed:9200:16:5ec5:2840:93a1, 2600:9000:25ed:9800:16:5ec5:2840:93a1, ...  
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:25ed:9000:16:5ec5:2840:93a1|:443... conn  
ected.  
HTTP request sent, awaiting response... 200 OK  
Length: 270 [application/octet-stream]  
Saving to: ‘runme.py’  
  
runme.py                    100%[=========================================>]     270  --.-KB/s    in 0s         
  
2024-09-17 23:54:53 (140 MB/s) - ‘runme.py’ saved [270/270]  
  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ ls  
fixme1.py  fixme2.py  level1.flag.txt.enc  level1.py  level2.flag.txt.enc  level2.py  runme.py  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ python3 runme.py    
picoCTF{run_s4n1ty_run}  
kali@KaliEND:~/Downloads/PicoCTF/parte2$
```
## Notas Adicionales 
solo era correr el .py
picoCTF{run_s4n1ty_run}

### Referencias


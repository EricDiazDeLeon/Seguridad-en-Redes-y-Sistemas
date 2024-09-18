## Objetivo 
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/659efd595171e4c40378be6a2e9b7298/Addadshashanammu.zip)
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/parte2$ wget https://mercury.picoctf.net/static/659efd595171e4c40378be6a2e9b7  
298/Addadshashanammu.zip  
--2024-09-17 23:56:03--  https://mercury.picoctf.net/static/659efd595171e4c40378be6a2e9b7298/Addadshashanammu.  
zip  
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142  
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.  
HTTP request sent, awaiting response... 200 OK  
Length: 4520 (4.4K) [application/octet-stream]  
Saving to: ‘Addadshashanammu.zip’  
  
Addadshashanammu.zip        100%[=========================================>]   4.41K  --.-KB/s    in 0s         
  
2024-09-17 23:56:03 (170 MB/s) - ‘Addadshashanammu.zip’ saved [4520/4520]  
  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ ls  
Addadshashanammu.zip  fixme2.py            level1.py            level2.py  
fixme1.py             level1.flag.txt.enc  level2.flag.txt.enc  runme.py  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ cd cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/  
Maelkashishi/Onnissiralis/Ularradallaku/  
bash: cd: too many arguments  
kali@KaliEND:~/Downloads/PicoCTF/parte2$ unzip Addadshashanammu.zip  
Archive:  Addadshashanammu.zip  
  creating: Addadshashanammu/  
  creating: Addadshashanammu/Almurbalarammi/  
  creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/  
  creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/  
  creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/  
  creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/  
  creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularrada  
llaku/  
 inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularrada  
llaku/fang-of-haynekhtnamet     
kali@KaliEND:~/Downloads/PicoCTF/parte2$ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Mae  
lkashishi/Onnissiralis/Ularradallaku/  
kali@KaliEND:~/Downloads/PicoCTF/parte2/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkas  
hishi/Onnissiralis/Ularradallaku$ ls  
fang-of-haynekhtnamet  
kali@KaliEND:~/Downloads/PicoCTF/parte2/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkas  
hishi/Onnissiralis/Ularradallaku$ ./fang-of-haynekhtnamet  
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_524e3dc4}  
kali@KaliEND:~/Downloads/PicoCTF/parte2/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkas  
hishi/Onnissiralis/Ularradallaku$
```
## Notas Adicionales 
era descomprimir el archivo que era muy largo y despues ontener la flag

### Referencias


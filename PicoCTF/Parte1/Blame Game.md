## Objetivo 
Someone's commits seems to be preventing the program from working. Who is it?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/74/challenge.zip)
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/parte1$ wget https://artifacts.picoctf.net/c_titan/74/challenge.zip  
--2024-09-17 22:13:30--  https://artifacts.picoctf.net/c_titan/74/challenge.zip  
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:4600:16:5ec5:2840:93a1, 2600:9000:25  
ed:c400:16:5ec5:2840:93a1, 2600:9000:25ed:5000:16:5ec5:2840:93a1, ...  
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:25ed:4600:16:5ec5:2840:93a1|:443... conn  
ected.  
HTTP request sent, awaiting response... 200 OK  
Length: 294122 (287K) [application/octet-stream]  
Saving to: ‘challenge.zip’  
  
challenge.zip               100%[=========================================>] 287.23K  --.-KB/s    in 0.1s       
  
2024-09-17 22:13:30 (2.65 MB/s) - ‘challenge.zip’ saved [294122/294122]  
  
kali@KaliEND:~/Downloads/PicoCTF/parte1$ ls  
challenge.zip  
kali@KaliEND:~/Downloads/PicoCTF/parte1$ unzip challenge.zip
kali@KaliEND:~/Downloads/PicoCTF/parte1$ cd drop-in/  
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ ls  
message.py  
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ cat message.py    
print("Hello, World!"  
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ git reflog  
bash: git: command not found  
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ git reflog  
faa685a (HEAD -> master) HEAD@{0}: commit: important business work  
8670d17 HEAD@{1}: commit: important business work  
525c5a7 HEAD@{2}: commit: important business work  
da9eb7e HEAD@{3}: commit: important business work  
4d5ff80 HEAD@{4}: commit: important business work  
c71bf89 HEAD@{5}: commit: important business work  
fe12631 HEAD@{6}: commit: important business work  
75a0aa1 HEAD@{7}: commit: important business work  
91c6239 HEAD@{8}: commit: important business work  
c6f8ab8 HEAD@{9}: commit: important business work  
ebbc004 HEAD@{10}: commit: important business work  
bc2ebc5 HEAD@{11}: commit: important business work  
f28c036 HEAD@{12}: commit: important business work  
faaf84c HEAD@{13}: commit: important business work  
ef599f8 HEAD@{14}: commit: important business work  
0135dc8 HEAD@{15}: commit: important business work  
5b2ab4b HEAD@{16}: commit: important business work  
e4cf77f HEAD@{17}: commit: important business work  
4713a09 HEAD@{18}: commit: important business work  
aff6442 HEAD@{19}: commit: important business work  
861d25a HEAD@{20}: commit: important business work  
9bf764c HEAD@{21}: commit: important business work  
88c3841 HEAD@{22}: commit: important business work  
25e9be8 HEAD@{23}: commit: important business work  
570f619 HEAD@{24}: commit: important business work  
0793931 HEAD@{25}: commit: important business work  
09c4082 HEAD@{26}: commit: important business work

kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ git log  
commit 8670d17387f8d7772c46a7cd0fb1b07c83580266 (HEAD)  
Author: picoCTF <ops@picoctf.com>  
Date:   Sat Mar 9 21:09:33 2024 +0000  
  
   important business work  
  
commit 525c5a7fb713c338bc58957e6502e6ef6845f8d7  
Author: picoCTF <ops@picoctf.com>  
Date:   Sat Mar 9 21:09:33 2024 +0000  
  
   important business work  
  
commit da9eb7ea7144162eb13bc2e3803405085f1004cb  
Author: picoCTF <ops@picoctf.com>  
Date:   Sat Mar 9 21:09:33 2024 +0000  
  
   important business work  
  
commit 4d5ff80609f265161fec5cdc42709e8b3fcacbc2  
Author: picoCTF <ops@picoctf.com>  
Date:   Sat Mar 9 21:09:33 2024 +0000  
  
   important business work  
  
commit c71bf891b81e783040b44a76d5a3326a2619a027  
Author: picoCTF <ops@picoctf.com>  
Date:   Sat Mar 9 21:09:33 2024 +0000
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ git blame message.py    
0fe87f16 (picoCTF{@sk_th3_1nt3rn_ea346835} 2024-03-09 21:09:25 +0000 1) print("Hello, World!"
```
## Notas Adicionales 
git blame es el comando usado para ver quien fue autor del commit que dejo incompleto el codigo .py
### Referencias


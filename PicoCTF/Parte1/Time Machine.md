## Objetivo 
What was I last working on? I remember writing a note to help me remember...You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/68/challenge.zip)
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/parte1$ wget https://artifacts.picoctf.net/c_titan/68/challenge.zip  
--2024-09-17 23:04:58--  https://artifacts.picoctf.net/c_titan/68/challenge.zip  
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:3a00:16:5ec5:2840:93a1, 2600:9000:25  
ed:b600:16:5ec5:2840:93a1, 2600:9000:25ed:6e00:16:5ec5:2840:93a1, ...  
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:25ed:3a00:16:5ec5:2840:93a1|:443... conn  
ected.  
HTTP request sent, awaiting response... 200 OK  
Length: 17738 (17K) [application/octet-stream]  
Saving to: ‘challenge.zip’  
  
challenge.zip               100%[=========================================>]  17.32K  --.-KB/s    in 0.02s      
  
2024-09-17 23:04:58 (732 KB/s) - ‘challenge.zip’ saved [17738/17738]  
  
kali@KaliEND:~/Downloads/PicoCTF/parte1$ ls  
challenge.zip  
kali@KaliEND:~/Downloads/PicoCTF/parte1$ unzip challenge.zip    
Archive:  challenge.zip  
  creating: drop-in/  
 inflating: drop-in/message.txt        
  creating: drop-in/.git/  
  creating: drop-in/.git/branches/  
 inflating: drop-in/.git/description     
  creating: drop-in/.git/hooks/  
 inflating: drop-in/.git/hooks/applypatch-msg.sample     
 inflating: drop-in/.git/hooks/commit-msg.sample     
 inflating: drop-in/.git/hooks/fsmonitor-watchman.sample     
 inflating: drop-in/.git/hooks/post-update.sample     
 inflating: drop-in/.git/hooks/pre-applypatch.sample     
 inflating: drop-in/.git/hooks/pre-commit.sample     
 inflating: drop-in/.git/hooks/pre-merge-commit.sample     
 inflating: drop-in/.git/hooks/pre-push.sample     
 inflating: drop-in/.git/hooks/pre-rebase.sample     
 inflating: drop-in/.git/hooks/pre-receive.sample     
 inflating: drop-in/.git/hooks/prepare-commit-msg.sample     
 inflating: drop-in/.git/hooks/update.sample     
  creating: drop-in/.git/info/  
 inflating: drop-in/.git/info/exclude     
  creating: drop-in/.git/refs/  
  creating: drop-in/.git/refs/heads/  
extracting: drop-in/.git/refs/heads/master     
  creating: drop-in/.git/refs/tags/  
extracting: drop-in/.git/HEAD          
 inflating: drop-in/.git/config        
  creating: drop-in/.git/objects/  
  creating: drop-in/.git/objects/pack/  
  creating: drop-in/.git/objects/info/  
  creating: drop-in/.git/objects/43/  
extracting: drop-in/.git/objects/43/246218ab4fc7b30e9a9dff073e012316851469     
  creating: drop-in/.git/objects/25/  
extracting: drop-in/.git/objects/25/16effb8d70e33bdd0023629b164a77225e1ec2     
  creating: drop-in/.git/objects/70/  
extracting: drop-in/.git/objects/70/5ff639b7846418603a3272ab54536e01e3dc43     
 inflating: drop-in/.git/index         
extracting: drop-in/.git/COMMIT_EDITMSG     
  creating: drop-in/.git/logs/  
 inflating: drop-in/.git/logs/HEAD     
  creating: drop-in/.git/logs/refs/  
  creating: drop-in/.git/logs/refs/heads/  
 inflating: drop-in/.git/logs/refs/heads/master     
kali@KaliEND:~/Downloads/PicoCTF/parte1$ ls  
challenge.zip  drop-in  
kali@KaliEND:~/Downloads/PicoCTF/parte1$ cd drop-in/  
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ ls  
message.txt  
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ cat message.txt    
This is what I was working on, but I'd need to look at my commit history to know why...kali@KaliEND:~/Download  
s/PicoCTF/parte1/drop-in$ git log  
commit 705ff639b7846418603a3272ab54536e01e3dc43 (HEAD -> master)  
Author: picoCTF <ops@picoctf.com>  
Date:   Sat Mar 9 21:10:36 2024 +0000  
  
   picoCTF{t1m3m@ch1n3_b476ca06}  
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$
```
## Notas Adicionales 
Este reto era solamente descargar el archivo, descomprimirlo y buscar los logs de git.
ahi estaba la flag: picoCTF{t1m3m@ch1n3_b476ca06}
### Referencias


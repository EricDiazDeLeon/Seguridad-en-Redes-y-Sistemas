## Objetivo 
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/177/challenge.zip)
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/parte1$ wget https://artifacts.picoctf.net/c_titan/177/challenge.zip  
--2024-09-17 22:35:05--  https://artifacts.picoctf.net/c_titan/177/challenge.zip  
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:a000:16:5ec5:2840:93a1, 2600:9000:25  
ed:aa00:16:5ec5:2840:93a1, 2600:9000:25ed:2200:16:5ec5:2840:93a1, ...  
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:25ed:a000:16:5ec5:2840:93a1|:443... conn  
ected.  
HTTP request sent, awaiting response... 200 OK  
Length: 24646 (24K) [application/octet-stream]  
Saving to: ‘challenge.zip’  
  
challenge.zip               100%[=========================================>]  24.07K  --.-KB/s    in 0.03s      
  
2024-09-17 22:35:05 (864 KB/s) - ‘challenge.zip’ saved [24646/24646]  
  
kali@KaliEND:~/Downloads/PicoCTF/parte1$ ls  
challenge.zip  
kali@KaliEND:~/Downloads/PicoCTF/parte1$ unzip challenge.zip    
Archive:  challenge.zip  
  creating: drop-in/  
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
extracting: drop-in/.git/refs/heads/main     
  creating: drop-in/.git/refs/heads/feature/  
extracting: drop-in/.git/refs/heads/feature/part-1     
extracting: drop-in/.git/refs/heads/feature/part-2     
extracting: drop-in/.git/refs/heads/feature/part-3     
  creating: drop-in/.git/refs/tags/  
extracting: drop-in/.git/HEAD          
 inflating: drop-in/.git/config        
  creating: drop-in/.git/objects/  
  creating: drop-in/.git/objects/pack/  
  creating: drop-in/.git/objects/info/  
  creating: drop-in/.git/objects/77/  
extracting: drop-in/.git/objects/77/d6ceca6fe23b57d88cf16f20003e10d6715690     
  creating: drop-in/.git/objects/b9/  
extracting: drop-in/.git/objects/b9/32e8c048154a46d224cd7691c99dc8cb88164a     
  creating: drop-in/.git/objects/d7/  
extracting: drop-in/.git/objects/d7/d09540eb1a24ed1299b230d143e6e93f9807eb     
  creating: drop-in/.git/objects/6e/  
extracting: drop-in/.git/objects/6e/17fb3a35364b4f9bb8bef8b5e6a5af2d3e7dfa     
  creating: drop-in/.git/objects/43/  
extracting: drop-in/.git/objects/43/e44dd37ba0c0adc3d78d0b85d699859ec8d75c     
  creating: drop-in/.git/objects/b2/  
extracting: drop-in/.git/objects/b2/e05429742e8784eee7dc83b6a9d1fb904988c0     
  creating: drop-in/.git/objects/7a/  
extracting: drop-in/.git/objects/7a/b4e25c0cd108374b2275fdb1fcdf635e591833     
  creating: drop-in/.git/objects/d1/  
extracting: drop-in/.git/objects/d1/f3407cee4479c075997b497fa290ca636fe258     
  creating: drop-in/.git/objects/e1/  
extracting: drop-in/.git/objects/e1/629c73b55d8831cfa3cda13a74c3e8f7c9e2f1     
  creating: drop-in/.git/objects/df/  
extracting: drop-in/.git/objects/df/ee6410cbf3457c318e6886dd7b13351bfb3e52     
  creating: drop-in/.git/objects/15/  
extracting: drop-in/.git/objects/15/613dd94d53ebb0e0c0530c7230563d6ecd65d1     
  creating: drop-in/.git/objects/8f/  
extracting: drop-in/.git/objects/8f/ccfcdaeeb259a51b642ba76ec2e5feb086c057     
 inflating: drop-in/.git/index         
extracting: drop-in/.git/COMMIT_EDITMSG     
  creating: drop-in/.git/logs/  
 inflating: drop-in/.git/logs/HEAD     
  creating: drop-in/.git/logs/refs/  
  creating: drop-in/.git/logs/refs/heads/  
 inflating: drop-in/.git/logs/refs/heads/main     
  creating: drop-in/.git/logs/refs/heads/feature/  
 inflating: drop-in/.git/logs/refs/heads/feature/part-1     
 inflating: drop-in/.git/logs/refs/heads/feature/part-2     
 inflating: drop-in/.git/logs/refs/heads/feature/part-3     
 inflating: drop-in/flag.py            
kali@KaliEND:~/Downloads/PicoCTF/parte1$ ls  
challenge.zip  drop-in  
kali@KaliEND:~/Downloads/PicoCTF/parte1$ cd drop-in/  
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ ls  
flag.py  
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ cat flag.py    
print("Printing the flag...")  
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ git branch  
 feature/part-1  
 feature/part-2  
 feature/part-3  
* main  
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ git checkout feature/part-1  
Switched to branch 'feature/part-1'  
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ cat flag.py    
print("Printing the flag...")  
print("picoCTF{t3@mw0rk_", end='')kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$git checkout feature/part-22  
Switched to branch 'feature/part-2'  
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ cat flag.py    
print("Printing the flag...")  
  
print("m@k3s_th3_dr3@m_", end='')kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ git checkout feature/part-3  
Switched to branch 'feature/part-3'  
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ cat flag.py    
print("Printing the flag...")  
  
print("w0rk_7ae8dd33}")
```
## Notas Adicionales 
buscar commits en diferentes branches y hacerle cat al .py
la flag es:
picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_7ae8dd33}
### Referencias


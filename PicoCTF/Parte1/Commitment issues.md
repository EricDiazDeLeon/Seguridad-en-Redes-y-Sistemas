## Objetivo 

## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/parte1$ wget https://artifacts.picoctf.net/c_titan/139/challenge.zip
--2024-09-17 22:41:08--  https://artifacts.picoctf.net/c_titan/139/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:4200:16:5ec5:2840:93a1, 2600:9000:25ed:fe00:16:5ec5:2840:93a1, 2600:9000:25ed:b000:16:5ec5:2840:93a1, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:25ed:4200:16:5ec5:2840:93a1|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 19193 (19K) [application/octet-stream]
Saving to: ‘challenge.zip’

challenge.zip               100%[=========================================>]  18.74K  --.-KB/s    in 0.01s   

2024-09-17 22:41:09 (1.46 MB/s) - ‘challenge.zip’ saved [19193/19193]

kali@KaliEND:~/Downloads/PicoCTF/parte1$ ls
challenge.zip
kali@KaliEND:~/Downloads/PicoCTF/parte1$ unzip challenge.zip 
Archive:  challenge.zip
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
 extracting: drop-in/.git/refs/heads/master  
   creating: drop-in/.git/refs/tags/
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
   creating: drop-in/.git/objects/
   creating: drop-in/.git/objects/pack/
   creating: drop-in/.git/objects/info/
   creating: drop-in/.git/objects/3a/
 extracting: drop-in/.git/objects/3a/71673f161f71dcf7758fc0a5844b126aad4daf  
   creating: drop-in/.git/objects/8a/
 extracting: drop-in/.git/objects/8a/b26439d85fcc8b4405ecc16f78141767b3f743  
   creating: drop-in/.git/objects/7d/
 extracting: drop-in/.git/objects/7d/3aa557ff7ba7d116badaf5307761efb3622249  
   creating: drop-in/.git/objects/d5/
 extracting: drop-in/.git/objects/d5/52d1ecd2d83fa2e65b6724d1ff73b45a7d59b7  
   creating: drop-in/.git/objects/0c/
 extracting: drop-in/.git/objects/0c/1ab266b7a3a1cd099bb509f82b7a2d03aecd03  
   creating: drop-in/.git/objects/14/
 extracting: drop-in/.git/objects/14/4fdc44b09058d7ea7f224121dfa5babadddbb9  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/master  
 extracting: drop-in/message.txt     
kali@KaliEND:~/Downloads/PicoCTF/parte1$ ls
challenge.zip  drop-in
kali@KaliEND:~/Downloads/PicoCTF/parte1$ cd drop-in/
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ ls
message.txt
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ cat message.txt 
TOP SECRET
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ git log
commit 144fdc44b09058d7ea7f224121dfa5babadddbb9 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:25 2024 +0000

    remove sensitive info

commit 7d3aa557ff7ba7d116badaf5307761efb3622249
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:25 2024 +0000

    create flag
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ git checkout 144fdc44b09058d7ea7f224121dfa5babadddbb9
Note: switching to '144fdc44b09058d7ea7f224121dfa5babadddbb9'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 144fdc4 remove sensitive info
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ ^C
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ ls
message.txt
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ cat message.txt 
TOP SECRET
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ git checkout 7d3aa557ff7ba7d116badaf5307761efb3622249
Previous HEAD position was 144fdc4 remove sensitive info
HEAD is now at 7d3aa55 create flag
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ ls
message.txt
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ cat message.txt 
picoCTF{s@n1t1z3_be3dd3da}
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$
```
## Notas Adicionales 
Dentro del directorio `drop-in/`, revisé los contenidos y encontré un archivo llamado `message.txt`. Al abrirlo con `cat`, leí el texto "TOP SECRET". Luego, usé `git log` para ver el historial de commits, observando dos commits relevantes: uno que mencionaba la eliminación de información sensible y otro relacionado con la creación de una "flag".

Posteriormente, cambié entre diferentes commits usando `git checkout`, primero al commit que eliminaba información sensible, y luego al commit que creaba la flag.
### Referencias

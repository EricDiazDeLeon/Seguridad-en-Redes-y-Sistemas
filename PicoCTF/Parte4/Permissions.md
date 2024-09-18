## Objetivo 
Can you read files in the root file?

Additional details will be available after launching your challenge instance.
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/parte4$ ssh -p 59546 picoplayer@saturn.picoctf.net  
The authenticity of host '[saturn.picoctf.net]:59546 ([13.59.203.175]:59546)' can't be established.  
ED25519 key fingerprint is SHA256:HKm/Bw1C+mhj23vO8tXULrgLFYvzP6gQH2IwgUiQTok.  
This host key is known by the following other names/addresses:  
   ~/.ssh/known_hosts:1: [hashed name]  
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes  
Warning: Permanently added '[saturn.picoctf.net]:59546' (ED25519) to the list of known hosts.  
picoplayer@saturn.picoctf.net's password:    
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 6.5.0-1023-aws x86_64)  
  
* Documentation:  https://help.ubuntu.com  
* Management:     https://landscape.canonical.com  
* Support:        https://ubuntu.com/advantage  
  
This system has been minimized by removing packages and content that are  
not required on a system that users do not log into.  
  
To restore this content, you can run the 'unminimize' command.  
  
The programs included with the Ubuntu system are free software;  
the exact distribution terms for each program are described in the  
individual files in /usr/share/doc/*/copyright.  
  
Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by  
applicable law.  
  
picoplayer@challenge:~$ ls /  
bin   challenge  etc   lib    lib64   media  opt   root  sbin  sys  usr  
boot  dev        home  lib32  libx32  mnt    proc  run   srv   tmp  var  
picoplayer@challenge:~$ sudo -l  
[sudo] password for picoplayer:    
Matching Defaults entries for picoplayer on challenge:  
   env_reset, mail_badpass,  
   secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin  
  
User picoplayer may run the following commands on challenge:  
   (ALL) /usr/bin/vi  
picoplayer@challenge:~$ sudo vi  
  
picoCTF{uS1ng_v1m_3dit0r_3dd6dcf4}  
  
Press ENTER or type command to continue  
picoplayer@challenge:~$
```
## Notas Adicionales 
use el comando sudo vi para abrir el editor vi con permisos de superusuario y posteriormente use ls -la para ver los archivos y vi que dentro habia un .txt oculto llamado .flag.txt y posteriormente hice cat /root/.flag.txt
### Referencias

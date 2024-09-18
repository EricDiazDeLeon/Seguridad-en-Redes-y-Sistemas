## Objetivo 
How to automate tasks to run at intervals on linux servers?

Additional details will be available after launching your challenge instance.
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/parte4$ ssh picoplayer@saturn.picoctf.net -p 52542  
The authenticity of host '[saturn.picoctf.net]:52542 ([13.59.203.175]:52542)' can't be established.  
ED25519 key fingerprint is SHA256:dMTscRrUiURy7uMu5eGWwEKdd2FzqLzx6LfWhssWnNQ.  
This key is not known by any other names.  
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes  
Warning: Permanently added '[saturn.picoctf.net]:52542' (ED25519) to the list of known hosts.  
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
  
picoplayer@challenge:~$ ls
picoplayer@challenge:~$ cd /etc/  
picoplayer@challenge:/etc$ ls  
adduser.conf            default       init.d         mailcap.order        rc0.d        subgid  
alternatives            deluser.conf  inputrc        mime.types           rc1.d        subgid-  
apt                     dhcp          issue          mke2fs.conf          rc2.d        subuid  
bash.bashrc             dpkg          issue.net      modules-load.d       rc3.d        subuid-  
bindresvport.blacklist  e2scrub.conf  kernel         mtab                 rc4.d        sudoers  
binfmt.d                environment   ld.so.cache    networkd-dispatcher  rc5.d        sudoers.d  
ca-certificates         fstab         ld.so.conf     networks             rc6.d        sysctl.conf  
ca-certificates.conf    gai.conf      ld.so.conf.d   nsswitch.conf        rcS.d        sysctl.d  
cloud                   group         legal          opt                  resolv.conf  systemd  
cron.d                  group-        libaudit.conf  os-release           rmt          terminfo  
cron.daily              gshadow       localtime      pam.conf             security     timezone  
cron.hourly             gshadow-      login.defs     pam.d                selinux      tmpfiles.d  
cron.monthly            gss           logrotate.d    passwd               shadow       ucf.conf  
cron.weekly             host.conf     lsb-release    passwd-              shadow-      ufw  
picoplayer@challenge:/etc$ cat /etc/crontab  
# picoCTF{Sch3DUL7NG_T45K3_L1NUX_1b4d8744}
```
## Notas Adicionales 
primero me conecte al servidor mediante ssh y despues busque la carpeta /etc/ y dentro de ella busque el archivo cron, que se llamaba crontab y le hice un cat.
### Referencias


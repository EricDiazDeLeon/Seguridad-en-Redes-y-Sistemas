## Objetivo 
Download this disk image, find the key and log into the remote machine.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download disk image](https://artifacts.picoctf.net/c/70/disk.img.gz)
- Remote machine: `ssh -i key_file -p 59522 ctf-player@saturn.picoctf.net`
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act17$ wget https://artifacts.picoctf.net/c/70/disk.img.gz
--2024-10-15 21:42:52--  https://artifacts.picoctf.net/c/70/disk.img.gz
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:3000:16:5ec5:2840:93a1, 2600:9000:25ed:3600:16:5ec5:2840:93a1, 2600:9000:25ed:6400:16:5ec5:2840:93a1, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:3000:16:5ec5:2840:93a1]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 48132743 (46M) [application/octet-stream]
Grabando a: «disk.img.gz»

disk.img.gz                      100%[========================================================>]  45,90M  2,74MB/s    en 16s     

2024-10-15 21:43:09 (2,84 MB/s) - «disk.img.gz» guardado [48132743/48132743]

kali@KaliEND:~/Downloads/PicoCTF/Act17$ ls
concat_v.png  dds1-alpine.flag.img  disk.img.gz
kali@KaliEND:~/Downloads/PicoCTF/Act17$ gzip -d disk.img.gz
kali@KaliEND:~/Downloads/PicoCTF/Act17$ ls
concat_v.png  dds1-alpine.flag.img  disk.img
kali@KaliEND:~/Downloads/PicoCTF/Act17$ mmls disk.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000471039   0000264192   Linux (0x83)
kali@KaliEND:~/Downloads/PicoCTF/Act17$ fls -o 0000206848 disk.img 470 -r
r/r 2344:       .ash_history
d/d 3916:       .ssh
+ r/r 2345:     id_ed25519
+ r/r 2346:     id_ed25519.pub
kali@KaliEND:~/Downloads/PicoCTF/Act17$ icat -o 0000206848 disk.img 2344  
ssh-keygen -t ed25519  
ls .ssh/  
halt  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ icat -o 0000206848 disk.img 2345  
-----BEGIN OPENSSH PRIVATE KEY-----  
b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW  
QyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLAAAAJgxpYKDMaWC  
gwAAAAtzc2gtZWQyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLA  
AAAECItu0F8DIjWxTp+KeMDvX1lQwYtUvP2SfSVOfMOChxYGCtd7hso2E7OQItY6aTjMMy  
KZb1FVmeBfnVjyHcGYosAAAADnJvb3RAbG9jYWxob3N0AQIDBAUGBw==  
-----END OPENSSH PRIVATE KEY-----
kali@KaliEND:~/Downloads/PicoCTF/Act17$ icat -o 0000206848 disk.img 2345 > key_file  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ chmod 600 key_file
kali@KaliEND:~/Downloads/PicoCTF/Act17$ ssh -i key_file -p 63536 ctf-player@saturn.picoctf.net  
The authenticity of host '[saturn.picoctf.net]:63536 ([13.59.203.175]:63536)' can't be established.  
ED25519 key fingerprint is SHA256:XBSvB1lk28EctsAVdKJtsl0A7C5bonqPrvHCYH8aEy4.  
This key is not known by any other names.  
Are you sure you want to continue connecting (yes/no/[fingerprint])? y  
Please type 'yes', 'no' or the fingerprint': yes  
Warning: Permanently added '[saturn.picoctf.net]:63536' (ED25519) to the list of known hosts.  
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
  
ctf-player@challenge:~$ ls -la  
total 4  
drwxr-xr-x 1 ctf-player ctf-player 20 Oct 16 03:57 .  
drwxr-xr-x 1 root       root       24 Aug  4  2023 ..  
drwx------ 2 ctf-player ctf-player 34 Oct 16 03:57 .cache  
drwxr-xr-x 2 ctf-player ctf-player 29 Aug  4  2023 .ssh  
-rw-r--r-- 1 root       root       28 Aug  4  2023 flag.txt  
ctf-player@challenge:~$ cat flag.txt    
picoCTF{k3y_5l3u7h_b5066e83}ctf-player@challenge:~$
```
## Notas Adicionales 
primero, bajé una imagen de disco de PicoCTF. La descomprimí y me puse a curiosear las particiones con mmls. Luego me dediqué a chismear los archivos dentro de la partición.
Lo interesante vino cuando encontré un archivo oculto .ash_history y una carpeta .ssh. Usé icat para echar un vistazo y di con una clave privada SSH. La guardé en un archivo aparte y le puse permisos para que nadie más la toqueteara.
Con la clave en mano, me conecté a un servidor remoto por SSH. Una vez dentro, encontré un archivo flag.txt que tenía la bandera que estaba buscando.
### Referencias


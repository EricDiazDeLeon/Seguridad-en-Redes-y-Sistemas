## Objetivo 
Download the disk image and use mmls on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag.
Note: if you are using the webshell, download and extract the disk image into /tmp not your home directory.
Download disk image
Access checker program: nc saturn.picoctf.net 49327
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act17$ wget https://artifacts.picoctf.net/c/137/disk.flag.img.gz  
--2024-10-15 22:29:21--  https://artifacts.picoctf.net/c/137/disk.flag.img.gz  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:8600:16:5ec5:2840:93a1, 2600:9000:25ed:9600:16:5ec5:28  
40:93a1, 2600:9000:25ed:b400:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:8600:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 47534568 (45M) [application/octet-stream]  
Grabando a: «disk.flag.img.gz»  
  
disk.flag.img.gz                 100%[========================================================>]  45,33M  5,22MB/s    en 9,6s       
  
2024-10-15 22:29:32 (4,74 MB/s) - «disk.flag.img.gz» guardado [47534568/47534568]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ ls  
disk.flag.img  disk.flag.img.gz  flag.txt  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ rm flag.txt    
kali@KaliEND:~/Downloads/PicoCTF/Act17$ rm disk.flag.img  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ ls  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ file disk.img.gz    
disk.img.gz: gzip compressed data, was "disk.img", last modified: Tue Sep 21 19:34:53 2021, from Unix, original size modulo 2^32 1  
04857600  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ gzip -d disk.img.gz    
kali@KaliEND:~/Downloads/PicoCTF/Act17$ ls  
disk.img  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ mmls disk.img  
DOS Partition Table  
Offset Sector: 0  
Units are in 512-byte sectors  
  
     Slot      Start        End          Length       Description  
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)  
001:  -------   0000000000   0000002047   0000002048   Unallocated  
002:  000:000   0000002048   0000204799   0000202752   Linux (0x83)  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ nc saturn.picoctf.net 49327  
What is the size of the Linux partition in the given disk image?  
Length in sectors: 0000202752                    
0000202752  
Great work!  
picoCTF{mm15_f7w!}
```
## Notas Adicionales 

### Referencias


## Objetivo 
Download this disk image and find the flag.
Note: if you are using the webshell, download and extract the disk image into /tmp not your home directory.
Download compressed disk image
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act17$ wget https://artifacts.picoctf.net/c/212/disk.flag.img.gz  
--2024-10-15 22:03:56--  https://artifacts.picoctf.net/c/212/disk.flag.img.gz  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:c200:16:5ec5:2840:93a1, 2600:9000:25ed:ae00:16:5ec5:28  
40:93a1, 2600:9000:25ed:d800:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:c200:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 44360923 (42M) [application/octet-stream]  
Grabando a: «disk.flag.img.gz»  
  
disk.flag.img.gz                 100%[========================================================>]  42,31M  2,11MB/s    en 16s        
  
2024-10-15 22:04:13 (2,65 MB/s) - «disk.flag.img.gz» guardado [44360923/44360923]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ gzip -d disk.flag.img.gz  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ ;s  
bash: error sintáctico cerca del elemento inesperado `;  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ ls  
concat_v.png  dds1-alpine.flag.img  disk.flag.img  disk.img  key_file  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ file disk.flag.img  
disk.flag.img: DOS/MBR boot sector; partition 1 : ID=0x83, active, start-CHS (0x0,32,33), end-CHS (0xc,223,19), startsector 2048,  
204800 sectors; partition 2 : ID=0x82, start-CHS (0xc,223,20), end-CHS (0x19,159,6), startsector 206848, 204800 sectors; partition  
3 : ID=0x83, start-CHS (0x19,159,7), end-CHS (0x32,253,11), startsector 411648, 407552 sectors  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ mmls disk.flag.img  
DOS Partition Table  
Offset Sector: 0  
Units are in 512-byte sectors  
  
     Slot      Start        End          Length       Description  
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)  
001:  -------   0000000000   0000002047   0000002048   Unallocated  
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)  
003:  000:001   0000206848   0000411647   0000204800   Linux Swap / Solaris x86 (0x82)  
004:  000:002   0000411648   0000819199   0000407552   Linux (0x83)  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ fls -o 0000411648 disk.flag.img  
d/d 460:        home  
d/d 11: lost+found  
d/d 12: boot  
d/d 13: etc  
d/d 81: proc  
d/d 82: dev  
d/d 83: tmp  
d/d 84: lib  
d/d 87: var  
d/d 96: usr  
d/d 106:        bin  
d/d 120:        sbin  
d/d 466:        media  
d/d 470:        mnt  
d/d 471:        opt  
d/d 472:        root  
d/d 473:        run  
d/d 475:        srv  
d/d 476:        sys  
d/d 2041:       swap  
V/V 51001:      $OrphanFiles  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ fls -o 0000411648 disk.flag.img 472  
r/r 1875:       .ash_history  
r/r * 1876(realloc):    flag.txt  
r/r 1782:       flag.txt.enc  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ icat -o 0000411648 disk.flag.img 1782  
Salted__0��!�-6V����0��U��l��&�:�pj_1�0�|�h  
                                          �Ȥ7� ���؎$�'%kali@KaliEND:~/Downloads/PicoCTF/Act17$ icat -o 0000411648 disk.flag.imxt.  
enc > flag.t                            icat -o 0000411648 disk.flag.imxt.enc > flag.t  
Missing image name and/or address  
usage: icat [-hrRsvV] [-f fstype] [-i imgtype] [-b dev_sector_size] [-o imgoffset] image [images] inum[-typ[-id]]  
       -h: Do not display holes in sparse files  
       -r: Recover deleted file  
       -R: Recover deleted file and suppress recovery errors  
       -s: Display slack space at end of file  
       -i imgtype: The format of the image file (use '-i list' for supported types)  
       -b dev_sector_size: The size (in bytes) of the device sectors  
       -f fstype: File system type (use '-f list' for supported types)  
       -o imgoffset: The offset of the file system in the image (in sectors)  
       -P pooltype: Pool container type (use '-P list' for supported types)  
       -B pool_volume_block: Starting block (for pool volumes only)  
       -S snap_id: Snapshot ID (for APFS only)  
       -v: verbose to stderr  
       -V: Print version  
       -k password: Decryption password for encrypted volumes

```
## Notas Adicionales 

### Referencias

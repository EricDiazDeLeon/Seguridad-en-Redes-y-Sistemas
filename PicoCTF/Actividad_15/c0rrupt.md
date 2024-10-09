## Objetivo 
We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act15$ wget https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/myster  
y  
--2024-10-07 11:01:48--  https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery  
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8  
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 202940 (198K) [application/octet-stream]  
Grabando a: «mystery»  
  
mystery                          100%[========================================================>] 198,18K   108KB/s    en 1,8s       
  
2024-10-07 11:01:53 (108 KB/s) - «mystery» guardado [202940/202940]
kali@KaliEND:~/Downloads/PicoCTF/Act15$ xxd -l 200 mystery    
00000000: 8965 4e34 0d0a b0aa 0000 000d 4322 4452  .eN4........C"DR  
00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..  
00000020: 7800 0000 0173 5247 4200 aece 1ce9 0000  x....sRGB.......  
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...  
00000040: 0009 7048 5973 aa00 1625 0000 1625 0149  ..pHYs...%...%.I  
00000050: 5224 f0aa aaff a5ab 4445 5478 5eec bd3f  R$......DETx^..?  
00000060: 8e64 cd71 bd2d 8b20 2080 9041 8302 08d0  .d.q.-.  ..A....  
00000070: f9ed 40a0 f36e 407b 9023 8f1e d720 8b3e  ..@..n@{.#... .>  
00000080: b7c1 0d70 0374 b503 ae41 6bf8 bea8 fbdc  ...p.t...Ak.....  
00000090: 3e7d 2a22 336f de5b 55dd 3d3d f920 9188  >}*"3o.[U.==. ..  
000000a0: 3871 2232 eb4f 57cf 14e6 25ff e5ff 5b2c  8q"2.OW...%...[,  
000000b0: 168b c562 b158 2c16 8bc5 62b1 582c 161d  ...b.X,...b.X,..  
000000c0: d6d7 678b c562 b158                      ..g..b.X  
kali@KaliEND:~/Downloads/PicoCTF/Act15$ hexedit mystery
kali@KaliEND:~/Downloads/PicoCTF/Act15$ exiftool mystery    
ExifTool Version Number         : 12.76  
File Name                       : mystery  
Directory                       : .  
File Size                       : 203 kB  
File Modification Date/Time     : 2024:10:07 11:08:01-06:00  
File Access Date/Time           : 2024:10:07 11:09:35-06:00  
File Inode Change Date/Time     : 2024:10:07 11:08:01-06:00  
File Permissions                : -rw-rw-r--  
Error                           : Unknown file type  
kali@KaliEND:~/Downloads/PicoCTF/Act15$ cp mystery flag.png  
kali@KaliEND:~/Downloads/PicoCTF/Act15$ ls  
flag.png  message.wav  mystery  sstv  whitepages.txt
kali@KaliEND:~/Downloads/PicoCTF/Act15$ cp mystery flag.png  
kali@KaliEND:~/Downloads/PicoCTF/Act15$ ls  
flag.png  message.wav  mystery  sstv  whitepages.txt  
kali@KaliEND:~/Downloads/PicoCTF/Act15$ pngcheck flag.png    
bash: pngcheck: orden no encontrada  
kali@KaliEND:~/Downloads/PicoCTF/Act15$ pngcheck -v flag.png    
zlib warning:  different version (expected 1.2.13, using 1.3.1)  
  
File: flag.png (202940 bytes)  
 this is neither a PNG or JNG image nor a MNG stream  
ERRORS DETECTED in flag.png  
kali@KaliEND:~/Downloads/PicoCTF/Act15$ hexedit flag.png    
kali@KaliEND:~/Downloads/PicoCTF/Act15$ pngcheck -v flag.png    
zlib warning:  different version (expected 1.2.13, using 1.3.1)  
  
File: flag.png (202940 bytes)  
 this is neither a PNG or JNG image nor a MNG stream  
ERRORS DETECTED in flag.png  
kali@KaliEND:~/Downloads/PicoCTF/Act15$ hexedit flag.png    
kali@KaliEND:~/Downloads/PicoCTF/Act15$ pngcheck -v flag.png    
zlib warning:  different version (expected 1.2.13, using 1.3.1)  
  
File: flag.png (202940 bytes)  
 invalid chunk name "C"DR" (43 22 44 52)  
ERRORS DETECTED in flag.png  
kali@KaliEND:~/Downloads/PicoCTF/Act15$ hexedit flag.png    
kali@KaliEND:~/Downloads/PicoCTF/Act15$ eog flag.png    
kali@KaliEND:~/Downloads/PicoCTF/Act15$ exiftool flag.png    
ExifTool Version Number         : 12.76  
File Name                       : flag.png  
Directory                       : .  
File Size                       : 203 kB  
File Modification Date/Time     : 2024:10:07 11:18:50-06:00  
File Access Date/Time           : 2024:10:07 11:18:56-06:00  
File Inode Change Date/Time     : 2024:10:07 11:18:50-06:00  
File Permissions                : -rw-rw-r--  
File Type                       : PNG  
File Type Extension             : png  
MIME Type                       : image/png  
Warning                         : PNG image did not start with IHDR  
SRGB Rendering                  : Perceptual  
Gamma                           : 2.2  
Pixels Per Unit X               : 5669  
Pixels Per Unit Y               : 5669  
Pixel Units                     : meters  
kali@KaliEND:~/Downloads/PicoCTF/Act15$ pngcheck -v flag.png    
zlib warning:  different version (expected 1.2.13, using 1.3.1)  
  
File: flag.png (202940 bytes)  
 invalid chunk name "C"DR" (43 22 44 52)  
ERRORS DETECTED in flag.png  
kali@KaliEND:~/Downloads/PicoCTF/Act15$ hexedit flag.png
```
## Notas Adicionales 
xxd permite ver un archivo en hexadecimal
modificamos el header del archivo danado con hexedit, despues identificamos los chunks corruptos del archivo y lo modificamos hasta que abrio la imagen.
picoCTF{c0rrupt10n_1847995}
### Referencias


## Objetivo
What do the [flags](https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png) mean?
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/flags$ wget https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199c  
dda2d253/flag.png  
--2024-11-21 17:30:52--  https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png  
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8  
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 43257 (42K) [application/octet-stream]  
Grabando a: «flag.png»  
  
flag.png                         100%[========================================================>]  42,24K  --.-KB/s    en 0s         
  
2024-11-21 17:30:52 (86,4 MB/s) - «flag.png» guardado [43257/43257]  
  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/flags$ ls  
flag.png  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/flags$ eog flag.png
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/flags$ exiftool flag.png    
ExifTool Version Number         : 12.76  
File Name                       : flag.png  
Directory                       : .  
File Size                       : 43 kB  
File Modification Date/Time     : 2020:10:26 12:30:20-06:00  
File Access Date/Time           : 2024:11:21 17:31:05-06:00  
File Inode Change Date/Time     : 2024:11:21 17:30:52-06:00  
File Permissions                : -rw-rw-r--  
File Type                       : PNG  
File Type Extension             : png  
MIME Type                       : image/png  
Image Width                     : 1642  
Image Height                    : 1095  
Bit Depth                       : 8  
Color Type                      : RGB  
Compression                     : Deflate/Inflate  
Filter                          : Adaptive  
Interlace                       : Noninterlaced  
SRGB Rendering                  : Perceptual  
Gamma                           : 2.2  
Pixels Per Unit X               : 5669  
Pixels Per Unit Y               : 5669  
Pixel Units                     : meters  
Image Size                      : 1642x1095  
Megapixels                      : 1.8  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/flags$

```
## Notas Adicionales
Descarge la imagen, y no parece haber nada en los metadatos, en la imagen solo aparecen banderas en la imagen por lo que...
la flag esta compuesta por las señales horarias marítimas internacionales de cada bandera.

flag: `picoCTF{F1AG5AND5TUFF}`
### Referencias
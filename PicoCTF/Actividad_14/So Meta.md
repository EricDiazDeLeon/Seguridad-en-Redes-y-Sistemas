## Objetivo 
Find the flag in this [picture](https://jupiter.challenges.picoctf.org/static/00efdf2961da1e21470ffc0d496c3cc2/pico_img.png).
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act14$ wget https://jupiter.challenges.picoctf.org/static/00efdf2961da1e21470ffc0d496c3cc2/pico_i  
mg.png  
--2024-10-03 23:35:31--  https://jupiter.challenges.picoctf.org/static/00efdf2961da1e21470ffc0d496c3cc2/pico_img.png  
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8  
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 108795 (106K) [application/octet-stream]  
Grabando a: «pico_img.png»  
  
pico_img.png                     100%[========================================================>] 106,25K   630KB/s    en 0,2s       
  
2024-10-03 23:35:31 (630 KB/s) - «pico_img.png» guardado [108795/108795]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act14$ ls  
capture.pcap  flag.txt  garden.jpg  pico_img.png  
kali@KaliEND:~/Downloads/PicoCTF/Act14$ exiftool pico_img.png    
ExifTool Version Number         : 12.76  
File Name                       : pico_img.png  
Directory                       : .  
File Size                       : 109 kB  
File Modification Date/Time     : 2020:10:26 12:38:23-06:00  
File Access Date/Time           : 2024:10:03 23:35:31-06:00  
File Inode Change Date/Time     : 2024:10:03 23:35:31-06:00  
File Permissions                : -rw-rw-r--  
File Type                       : PNG  
File Type Extension             : png  
MIME Type                       : image/png  
Image Width                     : 600  
Image Height                    : 600  
Bit Depth                       : 8  
Color Type                      : RGB  
Compression                     : Deflate/Inflate  
Filter                          : Adaptive  
Interlace                       : Noninterlaced  
Software                        : Adobe ImageReady  
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27  
Creator Tool                    : Adobe Photoshop CS6 (Windows)  
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B  
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B  
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B  
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B  
Warning                         : [minor] Text/EXIF chunk(s) found after PNG IDAT (may be ignored by some readers)  
Artist                          : picoCTF{s0_m3ta_fec06741}  
Image Size                      : 600x600  
Megapixels                      : 0.360
```
## Notas Adicionales 
Descargue la imagen con wget y use exiftool para ver los metadatos de la imagen y ahi estaba la flag en el campo del autor.
### Referencias


## Objetivo
Download this image file and find the flag.

- [Download image file](https://artifacts.picoctf.net/c/102/drawing.flag.svg)
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Examen2$ wget https://artifacts.picoctf.net/c/102/drawing.flag.svg  
--2024-10-26 17:25:45--  https://artifacts.picoctf.net/c/102/drawing.flag.svg  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:9800:16:5ec5:2840:93a1, 2600:9000:25ed:2e00:16:5ec5:28  
40:93a1, 2600:9000:25ed:7800:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:9800:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 4149 (4,1K) [application/octet-stream]  
Grabando a: «drawing.flag.svg»  
  
drawing.flag.svg                 100%[========================================================>]   4,05K  --.-KB/s    en 0s         
  
2024-10-26 17:25:45 (8,43 MB/s) - «drawing.flag.svg» guardado [4149/4149]  
  
kali@KaliEND:~/Downloads/PicoCTF/Examen2$ ls  
capture.flag.pcap  cat.jpg  drawing.flag.svg  file.des3  file.txt  
kali@KaliEND:~/Downloads/PicoCTF/Examen2$ exiftool drawing.flag.svg    
ExifTool Version Number         : 12.76  
File Name                       : drawing.flag.svg  
Directory                       : .  
File Size                       : 4.1 kB  
File Modification Date/Time     : 2023:03:15 21:16:47-06:00  
File Access Date/Time           : 2024:10:26 17:25:45-06:00  
File Inode Change Date/Time     : 2024:10:26 17:25:45-06:00  
File Permissions                : -rw-rw-r--  
File Type                       : SVG  
File Type Extension             : svg  
MIME Type                       : image/svg+xml  
Xmlns                           : http://www.w3.org/2000/svg  
Image Width                     : 210mm  
Image Height                    : 297mm  
View Box                        : 0 0 210 297  
SVG Version                     : 1.1  
ID                              : svg8  
Version                         : 0.92.5 (2060ec1f9f, 2020-04-08)  
Docname                         : drawing.svg  
Metadata ID                     : metadata5  
Work Format                     : image/svg+xml  
Work Type                       : http://purl.org/dc/dcmitype/StillImage  
Work Title                      :    
kali@KaliEND:~/Downloads/PicoCTF/Examen2$ strings drawing.flag.svg | grep pico  
kali@KaliEND:~/Downloads/PicoCTF/Examen2$ strings drawing.flag.svg | grep tspan  
      id="text3723"><tspan  
        id="tspan3748">p </tspan><tspan  
        id="tspan3754">i </tspan><tspan  
        id="tspan3756">c </tspan><tspan  
        id="tspan3758">o </tspan><tspan  
        id="tspan3760">C </tspan><tspan  
        id="tspan3762">T </tspan><tspan  
        id="tspan3764">F { 3 n h 4 n </tspan><tspan  
        id="tspan3752">c 3 d _ d 0 a 7 5 7 b f }</tspan></text>
kali@KaliEND:~/Downloads/PicoCTF/Examen2$
```
## Notas Adicionales
primero busque en los metadatos pero no encontre nada y despues le hice un grep a las strings del archivo para buscar "pico" a lo cual no encontre nada y finalmente haciendo el string sin nada se ven esas rows donde se describe la flag, entonces la filtre y encontre la flag.
flag: `picoCTF{3nh4nc3d_d0a757bf}`
### Referencias
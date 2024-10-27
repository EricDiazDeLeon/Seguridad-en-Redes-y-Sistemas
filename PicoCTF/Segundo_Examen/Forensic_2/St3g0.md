## Objetivo
Download this image and find the flag.

- [Download image](https://artifacts.picoctf.net/c/216/pico.flag.png)
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ wget https://artifacts.picoctf.net/c/216/pico.flag.png  
--2024-10-26 18:39:54--  https://artifacts.picoctf.net/c/216/pico.flag.png  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:5400:16:5ec5:2840:93a1, 2600:9000:25ed:1c00:16:5ec5:28  
40:93a1, 2600:9000:25ed:7200:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:5400:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 13441 (13K) [application/octet-stream]  
Grabando a: «pico.flag.png»  
  
pico.flag.png                    100%[========================================================>]  13,13K  --.-KB/s    en 0,03s      
  
2024-10-26 18:39:55 (484 KB/s) - «pico.flag.png» guardado [13441/13441]  
  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ ls  
Financial_Report_for_ABC_Labs.pdf  pico.flag.png  suspicious.dd.sda1  trace.pcap  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ eog pico.flag.png    
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ ls  
Financial_Report_for_ABC_Labs.pdf  pico.flag.png  stegsolve.jar  suspicious.dd.sda1  trace.pcap  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ java -jar stegsolve.jar    
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ zsteg pico.flag.png    
b1,rgb,lsb,xy       .. text: "picoCTF{7h3r3_15_n0_5p00n_a1062667}$t3g0"  
b1,abgr,lsb,xy      .. text: "E2A5q4E%uSA"  
b2,b,lsb,xy         .. text: "AAPAAQTAAA"  
b2,b,msb,xy         .. text: "HWUUUUUU"  
b3,r,lsb,xy         .. file: gfxboot compiled html help file  
b4,r,lsb,xy         .. file: Targa image data (16-273) 65536 x 4097 x 1 +4352 +4369 - 1-bit alpha - right "\021\020\001\001\021\02  
1\001\001\021\021\001"  
b4,g,lsb,xy         .. file: 0420 Alliant virtual executable not stripped  
b4,b,lsb,xy         .. file: Targa image data - Map 272 x 17 x 16 +257 +272 - 1-bit alpha "\020\001\021\001\021\020\020\001\020\00  
1\020\001"  
b4,bgr,lsb,xy       .. file: Targa image data - Map 273 x 272 x 16 +1 +4113 - 1-bit alpha "\020\001\001\001"  
b4,rgba,msb,xy      .. file: Applesoft BASIC program data, first line number 8  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$
```
## Notas Adicionales
use primero stegsolve para ver si habia algun texto escondido dentro de la imagen respecto a otras tonalidades de la misma imagen, lo cual no resulto ser el caso, entonces use zsteg y encontre la flag.
`picoCTF{7h3r3_15_n0_5p00n_a1062667}`
### Referencias
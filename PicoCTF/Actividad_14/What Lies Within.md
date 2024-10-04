## Objetivo 
There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?
## Solución  
```bash
  
buildings.png                    100%[========================================================>] 610,57K  1,01MB/s    en 0,6s       
  
2024-10-03 23:42:06 (1,01 MB/s) - «buildings.png» guardado [625219/625219]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act14$ ls  
buildings.png  capture.pcap  flag.txt  garden.jpg  pico_img.png  
kali@KaliEND:~/Downloads/PicoCTF/Act14$ eog buildings.png    
kali@KaliEND:~/Downloads/PicoCTF/Act14$ zsteg buildings.png    
b1,r,lsb,xy         .. text: "^5>R5YZrG"  
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"  
b1,abgr,msb,xy      .. file: PGP Secret Sub-key -  
b2,b,lsb,xy         .. text: "XuH}p#8Iy="  
b3,abgr,msb,xy      .. text: "t@Wp-_tH_v\r"  
b4,r,lsb,xy         .. text: "fdD\"\"\"\" "  
b4,r,msb,xy         .. text: "%Q#gpSv0c05"  
b4,g,lsb,xy         .. text: "fDfffDD\"\""  
b4,g,msb,xy         .. text: "f\"fff\"\"DD"  
b4,b,lsb,xy         .. text: "\"$BDDDDf"  
b4,b,msb,xy         .. text: "wwBDDDfUU53w"  
b4,rgb,msb,xy       .. text: "dUcv%F#A`"  
b4,bgr,msb,xy       .. text: " V\"c7Ga4"  
b4,abgr,msb,xy      .. text: "gOC_$_@o"  
kali@KaliEND:~/Downloads/PicoCTF/Act14$
```
## Notas Adicionales 
Descargué un archivo llamado buildings.png desde el sitio de PicoCTF utilizando el comando wget. Después de descargarlo, verifiqué que el archivo se guardó correctamente en mi directorio con el comando ls, y luego lo abrí usando eog para visualizarlo.

Posteriormente, utilicé la herramienta zsteg para analizar el archivo en busca de datos ocultos, dentro estaba la flag: `picoCTF{h1d1ng_1n_th3_b1t5}`.
### Referencias


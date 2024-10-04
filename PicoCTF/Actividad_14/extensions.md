## Objetivo 
This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act14$ wget https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.t  
xt  
--2024-10-03 23:24:29--  https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt  
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8  
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 9984 (9,8K) [application/octet-stream]  
Grabando a: «flag.txt»  
  
flag.txt                         100%[========================================================>]   9,75K  --.-KB/s    en 0s         
  
2024-10-03 23:24:29 (121 MB/s) - «flag.txt» guardado [9984/9984]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act14$ ls  
flag.txt  garden.jpg  
kali@KaliEND:~/Downloads/PicoCTF/Act14$ file flag.txt    
flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced
kali@KaliEND:~/Downloads/PicoCTF/Act14$ eog flag.txt
```
## Notas Adicionales 
el  .txt resulto ser una imagen asi que basto abrirla como una para obtener la imagen.
(use eye of the gnome para abrirla `eog`).
picoCTF{now_you_know_about_extensions}
### Referencias


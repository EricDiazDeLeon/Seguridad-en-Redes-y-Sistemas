## Objetivo 
This [garden](https://jupiter.challenges.picoctf.org/static/43c4743b3946f427e883f6b286f47467/garden.jpg) contains more than it seems.
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act14$ wget https://jupiter.challenges.picoctf.org/static/43c4743b3946f427e883f6b286f47467/garden  
.jpg  
--2024-10-03 23:21:03--  https://jupiter.challenges.picoctf.org/static/43c4743b3946f427e883f6b286f47467/garden.jpg  
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8  
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 2295192 (2,2M) [application/octet-stream]  
Grabando a: «garden.jpg»  
  
garden.jpg                       100%[========================================================>]   2,19M  1,22MB/s    en 1,8s       
  
2024-10-03 23:21:05 (1,22 MB/s) - «garden.jpg» guardado [2295192/2295192]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act14$ ls  
garden.jpg
kali@KaliEND:~/Downloads/PicoCTF/Act14$ strings garden.jpg | grep pico  
Here is a flag "picoCTF{more_than_m33ts_the_3y3657BaB2C}"
```
## Notas Adicionales 
Descargué un archivo llamado garden.jpg desde el sitio de PicoCTF utilizando el comando wget. La descarga fue exitosa, y verifiqué que el archivo con ls.
Para buscar información oculta dentro del archivo, usé el comando strings y filtré el resultado con grep buscando la palabra "pico". Esto me permitió encontrar el flag oculto dentro de la imagen: picoCTF{more_than_m33ts_the_3y3657BaB2C}.
### Referencias


## Objetivo
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/9f2d081f12c05202359632c1989e7927/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/9f2d081f12c05202359632c1989e7927/scrambled2.png)
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act20$ wget https://mercury.picoctf.net/static/9f2d081f12c05202359632c1989e7927/scrambled1.png  
--2024-10-23 10:52:05--  https://mercury.picoctf.net/static/9f2d081f12c05202359632c1989e7927/scrambled1.png  
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142  
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 197174 (193K) [application/octet-stream]  
Grabando a: «scrambled1.png»  
  
scrambled1.png                   100%[========================================================>] 192,55K  58,7KB/s    en 3,3s       
  
2024-10-23 10:52:18 (58,7 KB/s) - «scrambled1.png» guardado [197174/197174]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act20$ wget https://mercury.picoctf.net/static/9f2d081f12c05202359632c1989e7927/scrambled2.png  
--2024-10-23 10:52:27--  https://mercury.picoctf.net/static/9f2d081f12c05202359632c1989e7927/scrambled2.png  
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142  
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 197173 (193K) [application/octet-stream]  
Grabando a: «scrambled2.png»  
  
scrambled2.png                   100%[========================================================>] 192,55K  55,3KB/s    en 3,5s       
  
2024-10-23 10:52:40 (55,3 KB/s) - «scrambled2.png» guardado [197173/197173]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act20$ ls  
scrambled1.png  scrambled2.png  values  
kali@KaliEND:~/Downloads/PicoCTF/Act20$ eog scrambled  
kali@KaliEND:~/Downloads/PicoCTF/Act20$ eog scrambled2.png    
kali@KaliEND:~/Downloads/PicoCTF/Act20$ eog scrambled1.png
kali@KaliEND:~/Downloads/PicoCTF/Act20$ wget http://www.caesum.com/handbook/Stegsolve.jar -O stegsolve.jar  
--2024-10-23 10:55:46--  http://www.caesum.com/handbook/Stegsolve.jar  
Resolviendo www.caesum.com (www.caesum.com)... 216.234.165.33  
Conectando con www.caesum.com (www.caesum.com)[216.234.165.33]:80... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 312271 (305K) [application/x-java-archive]  
Grabando a: «stegsolve.jar»  
  
stegsolve.jar                    100%[========================================================>] 304,95K  62,5KB/s    en 4,9s       
  
2024-10-23 10:56:00 (62,5 KB/s) - «stegsolve.jar» guardado [312271/312271]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act20$ chmod +x stegsolve.jar  
kali@KaliEND:~/Downloads/PicoCTF/Act20$ mkdir bin  
kali@KaliEND:~/Downloads/PicoCTF/Act20$ mv stegsolve.jar bin/  
kali@KaliEND:~/Downloads/PicoCTF/Act20$ ls  
bin  scrambled1.png  scrambled2.png  values  
kali@KaliEND:~/Downloads/PicoCTF/Act20$ java -jar    
bin/            scrambled1.png  scrambled2.png  values             
kali@KaliEND:~/Downloads/PicoCTF/Act20$ cd bin/  
kali@KaliEND:~/Downloads/PicoCTF/Act20/bin$ ls  
stegsolve.jar  
kali@KaliEND:~/Downloads/PicoCTF/Act20/bin$ java -jar stegsolve.jar
```
## Notas Adicionales
convinamos las dos imagenes para obtener la flag usando una libreria llamada stegsolver.
`picoCTF{7188864c}`
sino en terminal se puede usar *imagemagick*:
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act20$ convert scrambled1.png  scrambled2.png -ompose Add -composite flag.png  
convert-im6.q16: unrecognized option `-ompose' @ error/convert.c/ConvertImageCommand/2290.  
kali@KaliEND:~/Downloads/PicoCTF/Act20$ convert scrambled1.png  scrambled2.png -compose Add -composite flag.png  
kali@KaliEND:~/Downloads/PicoCTF/Act20$ ls  
bin  flag.png  scrambled1.png  scrambled2.png  values  
kali@KaliEND:~/Downloads/PicoCTF/Act20$ eog flag.png
```
### Referencias
StageSolver:
https://github.com/zardus/ctf-tools/blob/master/stegsolve/install
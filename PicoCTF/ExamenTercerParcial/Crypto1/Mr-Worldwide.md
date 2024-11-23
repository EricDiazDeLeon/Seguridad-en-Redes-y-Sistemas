## Objetivo
A musician left us a [message](https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt). What's it mean?
## Solución
```bash
ali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/mrworldwide$ wget https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a3  
1f2a940409ad9d/message.txt  
--2024-11-21 17:55:29--  https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt  
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8  
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 278 [application/octet-stream]  
Grabando a: «message.txt»  
  
message.txt                      100%[========================================================>]     278  --.-KB/s    en 0s         
  
2024-11-21 17:55:29 (3,24 MB/s) - «message.txt» guardado [278/278]  
  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/mrworldwide$ ls  
message.txt  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/mrworldwide$ cat message.txt    
picoCTF{(35.028309, 135.753082)(46.469391, 30.740883)(39.758949, -84.191605)(41.015137, 28.979530)(24.466667, 54.366669)(3.140853,  
101.693207)_(9.005401, 38.763611)(-3.989038, -79.203560)(52.377956, 4.897070)(41.085651, -73.858467)(57.790001, -152.407227)(31.2  
05753, 29.924526)}
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/mrworldwide$

```
## Notas Adicionales
Dentro de el archivo .txt habia coordenadas geograficas, las cuales busque en google

Kyoto, Japan				         5.028309, 135.753082
Odessa, Ukraine		         46.469391, 30.740883	
Dayton, United States        39.758949, -84.191605		
Istanbul, Turkey			         41.015137, 28.979530 
Abu Dhabi, United Arab Emirates		24.466667, 54.366669
Kuala Lumpur, Malaysia		 	3.140853,  101.693207
_					
Addis Ababa, Ethiophia		 9.005401, 38.763611	
Loja, Ecuador				         -3.989038, -79.203560
Amsterdam, Netherlands	 52.377956, 4.897070		
Sleepy Hollow, United States  41.085651, -73.858467		
Kodiak, United States		 57.790001, -152.407227
Alexandria, Egypt                31.205753, 29.924526

entonces tomando la primera letra de cada ciudad obtenida obtenemos la bandera.
flag: `picoCTF{KODIAK_ALASKA}`
### Referencias
google maps
https://www.google.com/maps?hl=es
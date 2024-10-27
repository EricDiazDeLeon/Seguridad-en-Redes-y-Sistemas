## Objetivo
This image passes LSB statistical analysis, but we can't help but think there must be something to the visual artifacts present in this image...Download the image [here](https://artifacts.picoctf.net/c/303/Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png)
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_1$ wget https://artifacts.picoctf.net/c/303/Ninja-and-Prince-Genji-Ukiyoe-Utagaw  
a-Kunisada.flag.png  
--2024-10-26 23:39:16--  https://artifacts.picoctf.net/c/303/Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:6800:16:5ec5:2840:93a1, 2600:9000:25ed:7a00:16:5ec5:28  
40:93a1, 2600:9000:25ed:f600:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:6800:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 3354310 (3,2M) [application/octet-stream]  
Grabando a: «Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png»  
  
Ninja-and-Prince-Genji-Ukiyoe-Ut 100%[========================================================>]   3,20M  4,13MB/s    en 0,8s       
  
2024-10-26 23:39:17 (4,13 MB/s) - «Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png» guardado [3354310/3354310]  
  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_1$ ls  
dump.pcap  flag  flag.zip  Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_1$ eog Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png    
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_1$ ls  
dump.pcap  flag  flag.zip  Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png  stegsolve.jar  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_1$ java -jar stegsolve.jar    
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_1$ java -jar stegsolve.jar    
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_1$ ls  
dump.pcap  flag  flag.zip  Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png  stegsolve.jar  Texto.txt  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_1$ cat Texto.txt | grep Pico  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_1$ cat Texto.txt | grep pico  
220a7069636f4354 467b31355f793075  ".picoCT F{15_y0u  

```
## Notas Adicionales
use stegsolver para ver la data de la imagen, la guarde en un archivo y busque pico en el, despues de eso fui a esa linea del archivo, quite los espacios y complete la flag:
`picoCTF{15_y0ur_que57_qu1x071c_0r_h3r01c_24d55bee}`
### Referencias
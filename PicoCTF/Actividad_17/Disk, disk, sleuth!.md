## Objetivo 
Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image: [dds1-alpine.flag.img.gz](https://mercury.picoctf.net/static/f63e4eba644c99e92324b65cbd875db6/dds1-alpine.flag.img.gz)
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act17$ wget https://mercury.picoctf.net/static/f63e4eba644c99e92324b65cbd875db6/dds1-alpine.flag.img.gz
--2024-10-15 21:11:00--  https://mercury.picoctf.net/static/f63e4eba644c99e92324b65cbd875db6/dds1-alpine.flag.img.gz
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 29768910 (28M) [application/octet-stream]
Grabando a: «dds1-alpine.flag.img.gz»

dds1-alpine.flag.img.gz          100%[========================================================>]  28,39M  3,04MB/s    en 14s     

2024-10-15 21:11:14 (1,98 MB/s) - «dds1-alpine.flag.img.gz» guardado [29768910/29768910]

kali@KaliEND:~/Downloads/PicoCTF/Act17$ ls
dds1-alpine.flag.img.gz
kali@KaliEND:~/Downloads/PicoCTF/Act17$ gzip -d dds*.gz
kali@KaliEND:~/Downloads/PicoCTF/Act17$ strings dds1-alpine.flag.img | grep pico  
ffffffff81399ccf t pirq_pico_get  
ffffffff81399cee t pirq_pico_set  
ffffffff820adb46 t pico_router_probe  
 SAY picoCTF{f0r3ns1c4t0r_n30phyt3_ad5c96c0}
```
## Notas Adicionales 
descomprimimos todo del archivo .gz y obtenemos una imagen, al usar strings en el da muchisimas cosas por lo que se debe de hacer un grep al final para solo obtener lo deseado.
### Referencias


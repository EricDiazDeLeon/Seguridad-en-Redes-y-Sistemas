## Objetivo
Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it.Download the data [here](https://artifacts.picoctf.net/c/126/anthem.flag.txt).
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ wget https://artifacts.picoctf.net/c/126/anthem.flag.txt  
--2024-10-26 18:11:39--  https://artifacts.picoctf.net/c/126/anthem.flag.txt  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:7a00:16:5ec5:2840:93a1, 2600:9000:25ed:cc00:16:5ec5:28  
40:93a1, 2600:9000:25ed:7800:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:7a00:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 108668 (106K) [application/octet-stream]  
Grabando a: «anthem.flag.txt»  
  
anthem.flag.txt                  100%[========================================================>] 106,12K  --.-KB/s    en 0,09s      
  
2024-10-26 18:11:40 (1,12 MB/s) - «anthem.flag.txt» guardado [108668/108668]  
  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ ls  
anthem.flag.txt  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ wc anthem.flag.txt    
 2146  19139 108668 anthem.flag.txt
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ cat anthem.flag.txt | grep picoCTF  
     we think that the men of picoCTF{gr3p_15_@w3s0m3_2116b979}  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$
```
## Notas Adicionales
el archivo era un .txt muy grande con muchas lineas por lo que no convenia abrirlo y buscar manualmente, hice un grep y con eso basto.
flag: `picoCTF{gr3p_15_@w3s0m3_2116b979}`
### Referencias
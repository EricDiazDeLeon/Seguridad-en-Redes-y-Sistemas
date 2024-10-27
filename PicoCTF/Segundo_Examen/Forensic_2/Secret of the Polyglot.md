## Objetivo
The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/98/flag2of2-final.pdf).
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ wget https://artifacts.picoctf.net/c_titan/98/flag2of2-final.pdf  
--2024-10-26 17:54:00--  https://artifacts.picoctf.net/c_titan/98/flag2of2-final.pdf  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:cc00:16:5ec5:2840:93a1, 2600:9000:25ed:da00:16:5ec5:28  
40:93a1, 2600:9000:25ed:ca00:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:cc00:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 3362 (3,3K) [application/octet-stream]  
Grabando a: «flag2of2-final.pdf»  
  
flag2of2-final.pdf               100%[========================================================>]   3,28K  --.-KB/s    en 0s         
  
2024-10-26 17:54:00 (94,6 MB/s) - «flag2of2-final.pdf» guardado [3362/3362]  
  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ ls  
flag2of2-final.pdf
```
## Notas Adicionales
Este reto de verdad fue muy facil, la pista que nos dan es muy clara, al abrir el archivo pdf como un pdf normal obtenemos la primera parte de la flag:
`1n_pn9_&_pdf_1f991f77}`
posteriormente si lo abrimos como imagen ya sea cambiando la extension del archivo o simplemente usando imagemagick obtenemos la primera parte de la flag: `picoCTF{f1u3n7_`
flag completa: `picoCTF{f1u3n7_1n_pn9_&_pdf_1f991f77}`
### Referencias
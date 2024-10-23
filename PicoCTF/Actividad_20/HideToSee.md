## Objetivo
How about some hide and seek heh?Look at this image [here](https://artifacts.picoctf.net/c/236/atbash.jpg).
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act20$ wget https://artifacts.picoctf.net/c/236/atbash.jpg  
--2024-10-23 11:38:07--  https://artifacts.picoctf.net/c/236/atbash.jpg  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.100, 3.161.55.64, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[3.161.55.61]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 51512 (50K) [application/octet-stream]  
Grabando a: «atbash.jpg»  
  
atbash.jpg                       100%[========================================================>]  50,30K  --.-KB/s    en 0,08s      
  
2024-10-23 11:38:16 (637 KB/s) - «atbash.jpg» guardado [51512/51512]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act20$ ls  
atbash.jpg  bin  flag.png  message.txt  scrambled1.png  scrambled2.png  script.py  values  
kali@KaliEND:~/Downloads/PicoCTF/Act20$ eog atbash.jpg
kali@KaliEND:~/Downloads/PicoCTF/Act20$ steghide -extract -sf atbash.jpg    
steghide: comando desconocido "-extract".  
steghide: escriba "steghide --help" para la ayuda.  
kali@KaliEND:~/Downloads/PicoCTF/Act20$ steghide --extract -sf atbash.jpg    
Anotar salvoconducto:    
anot� los datos extra�dos e/"encrypted.txt".  
kali@KaliEND:~/Downloads/PicoCTF/Act20$ ls  
atbash.jpg  bin  encrypted.txt  flag.png  message.txt  scrambled1.png  scrambled2.png  script.py  values  
kali@KaliEND:~/Downloads/PicoCTF/Act20$ cat encrypted.txt    
krxlXGU{zgyzhs_xizxp_zx751vx6}
```
## Notas Adicionales
Descomprimimos la imagen usando steghide y obtuvimos una cadena que convertimos en cyberchef para obtener la flag:
`picoCTF{atbash_crack_ac751ec6}`
### Referencias
Cyberchef atbash Cipher
https://gchq.github.io/CyberChef/#recipe=Atbash_Cipher()&input=a3J4bFhHVXt6Z3l6aHNfeGl6eHBfeng3NTF2eDZ9

Steghide
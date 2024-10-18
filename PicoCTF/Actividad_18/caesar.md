## Objetivo 
Decrypt this [message](https://jupiter.challenges.picoctf.org/static/7d707a443e95054dc4cf30b1d9522ef0/ciphertext).
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act18$ wget https://jupiter.challenges.picoctf.org/static/7d707a443e95054dc4cf30b1d9522ef0/cipher  
text  
--2024-10-17 21:06:49--  https://jupiter.challenges.picoctf.org/static/7d707a443e95054dc4cf30b1d9522ef0/ciphertext  
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8  
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 35 [application/octet-stream]  
Grabando a: «ciphertext»  
  
ciphertext                       100%[========================================================>]      35  --.-KB/s    en 0s         
  
2024-10-17 21:06:49 (21,7 MB/s) - «ciphertext» guardado [35/35]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act18$ ls  
ciphertext  the_numbers.png  
kali@KaliEND:~/Downloads/PicoCTF/Act18$ cat ciphertext    
picoCTF{gvswwmrkxlivyfmgsrhnrisegl}kali@KaliEND:~/Downloads/PicoCTF/Act18$
```
## Notas Adicionales 
obtuvimos del archivo el texto: `picoCTF{gvswwmrkxlivyfmgsrhnrisegl}`
el cual no es una flag, almenos no completa resulta que tenemos que usar el algoritmo de cifrado caesar, por lo que necesitamos desplazar cada letra 1 espacio hasta que sea congruente.
esto tomo algunas rotaciones y el resultado fue: `picoCTF{crossingtherubicondjneoach}`
### Referencias
cyberchef
https://gchq.github.io/CyberChef/
## Objetivo 
Decode this [message](https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav) from the moon.
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act15$ wget https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/messag  
e.wav  
--2024-10-07 10:18:50--  https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav  
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8  
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 11066998 (11M) [application/octet-stream]  
Grabando a: «message.wav»  
  
message.wav                      100%[========================================================>]  10,55M   172KB/s    en 69s        
  
2024-10-07 10:20:03 (157 KB/s) - «message.wav» guardado [11066998/11066998]

```
## Notas Adicionales 
Lo primero que hice fue escuchar el archivo, pero como no tenía nada particularmente obvio, decidimos que teniamos que analizarlo más a fondo. Sabía que el reto probablemente implicaba convertir el sonido en algún tipo de visualización, así que abrí el audio en un editor como **Audacity** para echarle un vistazo. Una vez ahí, probé cambiar el formato del espectro y hacer una representación gráfica.

Y efectivamente, ahí estaba la magia. Al generar el espectrograma del audio, apareció una imagen bastante clara. A veces, los retos de este tipo tienen mensajes ocultos en la visualización del sonido, y esta vez no fue la excepción. La flag estaba incrustada en la imagen del espectrograma.

Así que, básicamente, el truco fue convertir la señal de audio en una imagen y, una vez hecho eso, leer la flag directamente desde la imagen.
`picoCTF{beep_boop_im_in_space}`
### Referencias


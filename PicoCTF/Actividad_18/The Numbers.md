## Objetivo 
The [numbers](https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png)... what do they mean?
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act18$ wget https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_nu  
mbers.png  
--2024-10-17 20:59:38--  https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png  
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8  
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 100721 (98K) [application/octet-stream]  
Grabando a: «the_numbers.png»  
  
the_numbers.png                  100%[========================================================>]  98,36K   581KB/s    en 0,2s       
  
2024-10-17 20:59:39 (581 KB/s) - «the_numbers.png» guardado [100721/100721]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act18$ ls  
the_numbers.png  
kali@KaliEND:~/Downloads/PicoCTF/Act18$ eog the_numbers.png    
kali@KaliEND:~/Downloads/PicoCTF/Act18$
```
## Notas Adicionales 
descarge la imagen y la abri con eye of the gnome, contiene una cadena de numeros y numeros entre corchetes, resulta que cada numero es el numero de letra en el abecedario es decir `a=1, b=2, c=3...`
entonces lo transformamos al abecedario y obenemos la flag:
`picoCTF{thenumbersmason}`
### Referencias


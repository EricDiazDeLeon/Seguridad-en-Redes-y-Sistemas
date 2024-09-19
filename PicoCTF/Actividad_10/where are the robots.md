## Objetivo 
Can you find the robots? https://jupiter.challenges.picoctf.org/problem/36474/ (link) or http://jupiter.challenges.picoctf.org:36474
## Solución  
```
https://jupiter.challenges.picoctf.org/problem/36474/robots.txt

despues copiamos de la pagina el disallow que es lo que el owner de la pagina no quiere que veamos.

User-agent: *
Disallow: /477ce.html

https://jupiter.challenges.picoctf.org/problem/36474/477ce.html
y por ultimo vamos a esa direccion y ahi se encuentra la flag:
Guess you found the robots  
picoCTF{ca1cu1at1ng_Mach1n3s_477ce}
```
## Notas Adicionales 
`robots.txt` es un archivo de texto simple que se coloca en la raíz de un sitio web para dar instrucciones a los rastreadores web (también conocidos como "bots" o "web crawlers").
### Referencias


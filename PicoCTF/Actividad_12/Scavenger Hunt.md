## Objetivo 
There is some interesting information hidden around this site [http://mercury.picoctf.net:44070/](http://mercury.picoctf.net:44070/). Can you find it?
## Solución  
```bash
Parte1:
<!-- Here's the first part of the flag: picoCTF{t -->

Parte2:
/* CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 */

Parte3:
User-agent: *
Disallow: /index.html
	# Part 3: t_0f_pl4c
# I think this is an apache server... can you Access the next flag?

Parte4:
# Part 4: 3s_2_lO0k
# I love making websites on my Mac, I can Store a lot of information there.

Parte5:
Congrats! You completed the scavenger hunt. Part 5: _7a46d25d}
```
## Notas Adicionales 
La pagina era solamente una pagina web sin funcionalidad alguna, al inspeccionar encontre las partes de la flag en diferentes lugares gracias a las pistas dejadas en cada paso, por ejemplo la primera parte estaba en el index del html, la segunda estaba en la hoja de estilos `css`, la tercera estaba en el archivo `robots.txt`, la cuarta en un archivo de configuracion del servidor apache `.htaccess` y la ultima estaba en un archivo llamado `.DS_Store` el cual es un archivo de mac que almacena informacion de la configuracion de carpetas.
la flag completa es: 
`picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_7a46d25d}`
### Referencias


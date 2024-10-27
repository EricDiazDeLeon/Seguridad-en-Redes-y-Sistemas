## Objetivo
The flag is somewhere on this web application not necessarily on the website. Find it.Check [this](http://saturn.picoctf.net:62374/) out.
## Solución
robots.txt:
```bash
User-agent *
Disallow: /cgi-bin/
Think you have seen your flag or want to keep looking.

ZmxhZzEudHh0;anMvbXlmaW
anMvbXlmaWxlLnR4dA==
svssshjweuiwl;oiho.bsvdaslejg
Disallow: /wp-admin/
```
## Notas Adicionales
ingresamos a la pagina, la inspeccionamos, despues vamos a robots.txt por que el nombre de el reto nos da la pista `http://saturn.picoctf.net:62374/robots.txt`
ahi encontramos texto en base 64 el cual copiamos y ponemos directamente en cyberchef:
`js/myfile.txt`
vamos a la direccion `http://saturn.picoctf.net:62374/js/myfile.txt`
y obtenemos la flag:
`picoCTF{Who_D03sN7_L1k5_90B0T5_718c9043}`
### Referencias
cyberchef from base 64
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=CmFuTXZiWGxtYVd4bExuUjRkQT09&oeol=VT
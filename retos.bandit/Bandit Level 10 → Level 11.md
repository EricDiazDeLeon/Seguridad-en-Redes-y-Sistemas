## Objetivo 
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data
## Datos de acceso al nivel 
bandit10
FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
## Solución  
```
bandit10@bandit:~$ ls
data.txt
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIGR0UjE3M2ZaS2IwUlJzREZTR3NnMlJXbnBOVmozcVJyCg==
bandit10@bandit:~$ cat data.txt | base64 -d
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
bandit10@bandit:~$
```

## Notas Adicionales 
base64 es  un esquema de decodificacion de binario  a texto de numeros del 0 al 9 y letras del abecedario (para decodificar textos en base 64).

### Referencias

python3 -modulo Base64
CyberChef [CyberChef (gchq.github.io)](https://gchq.github.io/CyberChef/)
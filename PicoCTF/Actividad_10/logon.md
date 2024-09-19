## Objetivo 
The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? `https://jupiter.challenges.picoctf.org/problem/13594/` ([link](https://jupiter.challenges.picoctf.org/problem/13594/)) or http://jupiter.challenges.picoctf.org:13594
## Solución  
```bash
Success: You logged in! Not sure youll be able to see the flag though.
**No flag for you**

### Factory Login

**Flag**: `picoCTF{th3_c0nsp1r4cy_l1v3s_d1c24fef}`
```
## Notas Adicionales 
al inciar sesion se inicia correctamente pero no nos da ninguna flag por que no somos el usuario correcto (permisos).
Lo que tenemos que hacer es cambiar la cookie de inicio de sesion para que al momento de autenticarse se autentique como administrador y poder ver la FLAG.
### Referencias


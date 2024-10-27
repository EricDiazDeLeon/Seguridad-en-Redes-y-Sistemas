## Objetivo
Can you get the flag?Go to this [website](http://saturn.picoctf.net:51549/) and see what you can discover.
## Solución
secure.js
```bash
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}


```
## Notas Adicionales
hay una pagina de registro en este reto, ingresamos informacion random y entonces verificamos la pestaña de network y vemos que hay un php trabajando, al inspeccionarlo vemos que hace referencia a un archivo llamado secure.js donde se encuentra la info de inicio de sesion del admin.
al ingresar como admin obtenemos la bandera:
flag: `picoCTF{j5_15_7r4n5p4r3n7_a8788e61}`
### Referencias
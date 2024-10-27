## Objetivo
My dog-sitter's brother made this website but I can't get in; can you help?
login.mars.picoctf.net
## Solución
index.js
```bash
(async()=>{await new Promise((e=>window.addEventListener("load",e))),document.querySelector("form").addEventListener("submit",(e=>{e.preventDefault();const r={u:"input[name=username]",p:"input[name=password]"},t={};for(const e in r)t[e]=btoa(document.querySelector(r[e]).value).replace(/=/g,"");return"YWRtaW4"!==t.u?alert("Incorrect Username"):"cGljb0NURns1M3J2M3JfNTNydjNyXzUzcnYzcl81M3J2M3JfNTNydjNyfQ"!==t.p?alert("Incorrect Password"):void alert(`Correct Password! Your flag is ${atob(t.p)}.`)}))})();
```
## Notas Adicionales
inspeccionamos el codigo de la pagina y dentro de ella no hay mucho, nos movemos a index.js donde hay un codigo muy largo, pero dentro de el encontramos un string que parece ser la contrasena del login de la pagina, asi que vamos a cyberchef y la desencriptamos de base64 y obtenemos la flag.
`picoCTF{53rv3r_53rv3r_53rv3r_53rv3r_53rv3r}`
### Referencias
cyberchef from base64
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnMxTTNKMk0zSmZOVE55ZGpOeVh6VXpjbll6Y2w4MU0zSjJNM0pmTlROeWRqTnlmUQ

beutifier
https://beautifier.io/
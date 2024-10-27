## Objetivo
The developer of this website mistakenly left an important artifact in the website source, can you find it?The website is [here](http://saturn.picoctf.net:49674/)
## Solución
```bash
/** banner_main picoCTF{1nsp3ti0n_0f_w3bpag3s_8de925a7} **/
 .carousel-indicators li {
     width: 20px;
     height: 20px;
     border-radius: 11px;
     background-color: #070000;
}
 .carousel-indicators li.active {
    background-color: #35a30a;
}
```
## Notas Adicionales
La flag se encontraba en los css de la pagina.
`picoCTF{1nsp3ti0n_0f_w3bpag3s_8de925a7}`
### Referencias
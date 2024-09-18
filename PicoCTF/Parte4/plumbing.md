## Objetivo 
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 7480`.
## Solución  
```bash
Not a flag either  
Not a flag either  
I don't think this is a flag either  
Not a flag either  
Again, I really don't think this is a flag  
Not a flag either  
I don't think this is a flag either  
I don't think this is a flag either  
Again, I really don't think this is a flag  
I don't think this is a flag either  
Again, I really don't think this is a flag  
This is defintely not a flag  
Not a flag either  
Not a flag either  
Not a flag either  
I don't think this is a flag either  
I don't think this is a flag either  
Not a flag either  
Not a flag either  
This is defintely not a flag  
This is defintely not a flag  
Again, I really don't think this is a flag  
Not a flag either  
Not a flag either  
Not a flag either  
kali@KaliEND:~/Downloads/PicoCTF/parte4$ nc jupiter.challenges.picoctf.org 7480 | grep picoCTF  
picoCTF{digital_plumb3r_06e9d954}
```
## Notas Adicionales 
al conectarnme usando netcat sale muchisimo texto por lo cual use un grep para filtrar solo lo que estaba buscando.
### Referencias


## Objetivo 
Theres tapping coming in from the wires. What's it saying `nc jupiter.challenges.picoctf.org 9422`.
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act18$ nc jupiter.challenges.picoctf.org 9422  
.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. ..--- -.... ---.. ...-- ---.. ..-  
-- ....- -.... .---- ----- }    
kali@KaliEND:~/Downloads/PicoCTF/Act18$
```
## Notas Adicionales 
al conectarme al servidor nos da un codigo de puntos y guiones lo cual rapidamente interprete que era codigo morse, use cyberchef para decifrarlo y la flag es: `PICOCTF{M0RS3C0D31SFUN2683824610}`
### Referencias
cyberchef-fromMorse
https://gchq.github.io/CyberChef/#recipe=From_Morse_Code('Space','Line%20feed')&input=Li0tLiAuLiAtLi0uIC0tLSAtLi0uIC0gLi4tLiB7IC0tIC0tLS0tIC4tLiAuLi4gLi4uLS0gLS4tLiAtLS0tLSAtLi4gLi4uLS0gLi0tLS0gLi4uIC4uLS4gLi4tIC0uIC4uLS0tIC0uLi4uIC0tLS4uIC4uLi0tIC0tLS4uIC4uLS0tIC4uLi4tIC0uLi4uIC4tLS0tIC0tLS0tIH0g
## Objetivo 
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29221`.
## Solución  
```bash
kali@KaliEND:~$ nc jupiter.challenges.picoctf.org 29221  
Let us see how data is stored  
animation  
Please give the 01100001 01101110 01101001 01101101 01100001 01110100 01101001 01101111 01101110 as a word.  
...  
you have 45 seconds.....  
  
Input:  
animation  
Please give me the  164 145 163 164 as a word.  
Input:  
test  
Please give me the 6c616d70 as a word.  
Input:  
lamp  
You've beaten the challenge  
Flag: picoCTF{learning_about_converting_values_00a975ff}  
kali@KaliEND:~$
```
## Notas Adicionales 
te da 45 segundos para pasar codigos binarios a palabras, si te equivocas se cierra la coneccion y toca volverlo a intentar, como dato es random, me costo algunos intentos.
### Referencias
Cyberchef
https://gchq.github.io/CyberChef/
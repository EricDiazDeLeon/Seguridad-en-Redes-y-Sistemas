## Objetivo
'Suspicious' is written all over this disk image. Download [suspicious.dd.sda1](https://jupiter.challenges.picoctf.org/static/c4852a91e1d0d180c75af188ea8d8a2c/suspicious.dd.sda1)
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ wget https://jupiter.challenges.picoctf.org/static/c4852a91e1d0d180c75af188ea  
8d8a2c/suspicious.dd.sda1  
--2024-10-26 18:26:04--  https://jupiter.challenges.picoctf.org/static/c4852a91e1d0d180c75af188ea8d8a2c/suspicious.dd.sda1  
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8  
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 32868864 (31M) [application/octet-stream]  
Grabando a: «suspicious.dd.sda1»  
  
suspicious.dd.sda1               100%[========================================================>]  31,35M  2,30MB/s    en 14s        
  
2024-10-26 18:26:18 (2,22 MB/s) - «suspicious.dd.sda1» guardado [32868864/32868864]  
  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ strings -e b suspicious.dd.sda1    
6fa0925f_3<_|Lm_111t5_3b{FTCocip  
qQWTYUiIOPb  
FGjJKLs  
ZXvc  
#+3;CScs  
!1Aa  
qQWTYUiIOPb  
FGjJKLs  
ZXvc  
#+3;CScs  
!1Aa  
#+3;CScs  
!1Aa  
7777777777  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ strings -e b suspicious.dd.sda1 | rev  
picoCTF{b3_5t111_mL|_<3_f5290af6  
bPOIiUYTWQq  
sLKJjGF  
cvXZ  
scSC;3+#  
aA1!  
bPOIiUYTWQq  
sLKJjGF  
cvXZ  
scSC;3+#  
aA1!  
scSC;3+#  
aA1!  
7777777777  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$
```
## Notas Adicionales
usamos strings en el archivo para buscar la flag, -e significa codificación y `b` significa byte. Especifica el tipo de codificación, vemos la flag pero se encuentra al revez, por lo que usamos `| rev` que significa revertir, por lo que el texto estaría al revés y por lo tanto la flag estaria en su estado correcto.
`picoCTF{b3_5t111_mL|_<3_f5290af6}`
### Referencias
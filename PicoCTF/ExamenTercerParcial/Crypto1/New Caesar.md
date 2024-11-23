## Objetivo
We found a brand new type of encryption, can you break the secret code? (Wrap with picoCTF{}) `lkmjkemjmkiekeijiiigljlhilihliikiliginliljimiklligljiflhiniiiniiihlhilimlhijil` [new_caesar.py](https://mercury.picoctf.net/static/c9043977604318594ab73d126a01d0b1/new_caesar.py)
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/newcaesar$ wget  
https://mercury.picoctf.net/static/c9043977604318594ab73d126a0  
1d0b1/new_caesar.py  
--2024-11-21 18:09:31--  https://mercury.picoctf.net/static/c90  
43977604318594ab73d126a01d0b1/new_caesar.py  
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189  
.209.142  
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189  
.209.142]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 589 [application/octet-stream]  
Grabando a: «new_caesar.py»  
  
new_caesar.py                    100%[=========================  
===============================>]     589  --.-KB/s    en 0s      
  
2024-11-21 18:09:32 (9,49 MB/s) - «new_caesar.py» guardado [589  
/589]  
  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/newcaesar$ ls  
new_caesar.py  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/newcaesar$ nanp  
new_caesar.py    
bash: nanp: orden no encontrada  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/newcaesar$ nano  
new_caesar.py
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/newcaesar$ nano  
solve.py  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/newcaesar$ cat  
solve.py    
import string  
  
LOWERCASE_OFFSET = ord("a")  
ALPHABET = string.ascii_lowercase[:16]  
  
def b16_decode(cipher):  
   dec = ""  
   for c in range(0, len(cipher), 2):  
       b = ""  
       b += "{0:04b}".format(ALPHABET.index(cipher[c]))  
       b += "{0:04b}".format(ALPHABET.index(cipher[c + 1]))  
       dec += chr(int(b, 2))  
   return dec  
  
def unshift(c, k):  
   t1 = ord(c) - LOWERCASE_OFFSET  
   t2 = ord(k) - LOWERCASE_OFFSET  
   return ALPHABET[(t1 - t2) % len(ALPHABET)]  
  
enc = "lkmjkemjmkiekeijiiigljlhilihliikiliginliljimiklligljiflh  
iniiiniiihlhilimlhijil"  
  
for key in ALPHABET:  
   s = ""  
   for i, c in enumerate(enc):  
       s += unshift(c, key[i % len(key)])  
   s = b16_decode(s)  
   print(s)
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/newcaesar$ python3 solve.py 
ºÉ¤ÉÊ¤¹·¸¸¹»¹···
©¸¸¹sxwu¨¦zv§yzu|§¨{yªu¨t¦|w|wv¦z{¦xz
§§¨bgfdiehidkjhdckfkfeijgi
qQqVUSXTWXSZYWSRZUZUTXYVX
v`@`EDBusGCtFGBItuHFwBuAsIDIDCsGHsEG
et_tu?_431db62c5618cd75f1d0b83832b67b46
TcNcd.N#" SQ%!R$% 'RS&$U S/Q'"'"!Q%&Q#%
CR=RS=B@AABDB@@@
2A,AB
???  ,1?00131
!01ûÿý .òþ/ñòýô/ óñ"ý ü.ôÿôÿþ.òó.ðò
/
/ ê
ïîìáíàáìãâàìëãîãîíáâïá
ùÙùÞÝÛ
ÑßÛÚ  ÐÜ
    ÒÝÒÝÜ
         ÐÑ
           ÞÐ
ÈèÍÌÊýûÏËüÎÏÊÁüýÀÎÿÊýÉûÁÌÁÌËûÏÀûÍÏ
íü×üý·×¼»¹ìê¾ºë½¾¹°ëì¿½î¹ì¸ê°»°»ºê¾¿ê¼¾
ÜëÆëì¦Æ«ª¨ÛÙ­©Ú¬­¨¯ÚÛ®¬Ý¨Û§Ù¯ª¯ª©Ù­®Ù«­
ËÚµÚÛµÊÈÉÉÊÊÈÈÈ

```
## Notas Adicionales

`picoCTF{et_tu?_431db62c5618cd75f1d0b83832b67b46}`
### Referencias
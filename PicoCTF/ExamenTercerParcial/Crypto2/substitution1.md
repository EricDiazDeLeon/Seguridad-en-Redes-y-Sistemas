## Objetivo
A second message has come in the mail, and it seems almost identical to the first one. Maybe the same thing will work again.Download the message [here](https://artifacts.picoctf.net/c/183/message.txt).
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/substitution1$ wget https://artifacts.picoctf.net/c/183/message.txt  
--2024-11-22 22:58:30--  https://artifacts.picoctf.net/c/183/message.txt  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:6e00:16:5ec5:2840:93a1, 2600:9000:25ed:7200:16:5ec5:28  
40:93a1, 2600:9000:25ed:7c00:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:6e00:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 638 [application/octet-stream]  
Grabando a: «message.txt»  
  
message.txt                      100%[========================================================>]     638  --.-KB/s    en 0s         
  
2024-11-22 22:58:31 (9,62 MB/s) - «message.txt» guardado [638/638]  
  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/substitution1$ ls  
message.txt  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/substitution1$ cat message.txt    
LKOb (bwvek ove lgqkhej kwj osgx) gej g kyqj vo lvrqhkje bjlhetky lvrqjktktvu. Lvukjbkgukb gej qejbjukjz dtkw g bjk vo lwgssjuxjb  
dwtlw kjbk kwjte lejgktftky, kjlwutlgs (guz xvvxstux) bitssb, guz qevmsjr-bvsftux gmtstky. Lwgssjuxjb hbhgssy lvfje g uhrmje vo lg  
kjxvetjb, guz dwju bvsfjz, jglw ytjszb g bketux (lgssjz g osgx) dwtlw tb bhmrtkkjz kv gu vustuj blvetux bjeftlj. LKOb gej g xejgk  
dgy kv sjgeu g dtzj geegy vo lvrqhkje bjlhetky bitssb tu g bgoj, sjxgs juftevurjuk, guz gej wvbkjz guz qsgyjz my rguy bjlhetky xev  
hqb gevhuz kwj dvesz ove ohu guz qeglktlj. Ove kwtb qevmsjr, kwj osgx tb: qtlvLKO{OE3AH3ULY_4774LI5_4E3_L001_6J0659OM}kali@KaliEND  
:~/Downloads/PicoCTF/Exam3erParcial/substitution1$
```
## Notas Adicionales
usando https://quipqiup.com/ desciframos el mensaje.
flag: `picoCTF{FR3QU3NCY_4774CK5_4R3_C001_6E0659FB}`
### Referencias
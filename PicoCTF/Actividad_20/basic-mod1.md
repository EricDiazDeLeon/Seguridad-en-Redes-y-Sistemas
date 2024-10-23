## Objetivo
We found this weird message being passed around on the servers, we think we have a working decryption scheme.Download the message [here](https://artifacts.picoctf.net/c/129/message.txt).Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act20$ wget https://artifacts.picoctf.net/c/129/message.txt  
--2024-10-23 11:20:06--  https://artifacts.picoctf.net/c/129/message.txt  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.64, 3.161.55.61, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[3.161.55.100]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 86 [application/octet-stream]  
Grabando a: «message.txt»  
  
message.txt                      100%[========================================================>]      86  --.-KB/s    en 0s         
  
2024-10-23 11:20:15 (47,8 MB/s) - «message.txt» guardado [86/86]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act20$ ls  
bin  flag.png  message.txt  scrambled1.png  scrambled2.png  values  
kali@KaliEND:~/Downloads/PicoCTF/Act20$ cat message.txt    
350 63 353 198 114 369 346 184 202 322 94 235 114 110 185 188 225 212 366 374 261 213 kali@KaliEND:~/Downloads/PicoCTF/Act20$ nano  
script.py
kali@KaliEND:~/Downloads/PicoCTF/Act20$ python3 script.py  
350  
63  
353  
198  
114  
369  
346  
184  
202  
322  
94  
235  
114  
110  
185  
188  
225  
212  
366  
374  
261  
213
```
script.py:
```bash
data = open('message.txt', 'r').read().split()  
for c in data:  
       print(c)
```

```bash
kali@KaliEND:~/Downloads/PicoCTF/Act20$ python3 script.py  
R  
0  
U  
N  
D  
_  
N  
_  
R  
0  
U  
N  
D  
_  
A  
D  
D  
1  
7  
E  
C  
2  
R0UND_N_R0UND_ADD17EC2
```
script.py:
```bash
data = open('message.txt', 'r').read().split()  
flag = ''  
for c in data:  
       char = int(c) % 37  
       if char >= 0 and char <= 25:  
               s = chr(char+65)  
       elif char >= 26 and char <=35:  
               s = chr(char+22)  
       elif char == 36:  
               s = '_'  
       flag += s  
       print(s)  
print(flag)
```
## Notas Adicionales
Le hicimos un modulo de 37 a cada conjunto de números y remplazamos también donde se encontrara el numero 36 por un `_` 
usando python para al final obtener: `R0UND_N_R0UND_ADD17EC2`
`picoCTF{R0UND_N_R0UND_ADD17EC2}`
### Referencias
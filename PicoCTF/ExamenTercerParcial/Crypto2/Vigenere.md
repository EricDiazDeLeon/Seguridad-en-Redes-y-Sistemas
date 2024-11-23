## Objetivo
Can you decrypt this message?Decrypt this [message](https://artifacts.picoctf.net/c/159/cipher.txt) using this key "CYLAB".
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/Vigenere$ wget https://artifacts.picoctf.net/c/159/cipher.txt  
--2024-11-22 23:02:46--  https://artifacts.picoctf.net/c/159/cipher.txt  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:4a00:16:5ec5:2840:93a1, 2600:9000:25ed:c00:16:5ec5:284  
0:93a1, 2600:9000:25ed:f200:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:4a00:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 43 [application/octet-stream]  
Grabando a: «cipher.txt»  
  
cipher.txt                       100%[========================================================>]      43  --.-KB/s    en 0s         
  
2024-11-22 23:02:47 (22,5 MB/s) - «cipher.txt» guardado [43/43]  
  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/Vigenere$ ls  
cipher.txt  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/Vigenere$ cat cipher.txt    
rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_f85729e7}  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/Vigenere$ nano solve.py  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/Vigenere$    
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/Vigenere$ nano solve.py
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/Vigenere$ python3 solve.py    
picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_d85729g7}
```
solve.py:
```bash
import string

instr = "rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_2951c89f}"
key = "CYLAB"
outstr = ""

offset_lower = ord('a')
offset_upper = ord('A')
lower = string.ascii_lowercase
upper = string.ascii_uppercase

# Diccionarios para las letras minúsculas
dicts_l = {}
for k in key:
    key_loc = ord(k) - offset_upper
    dicts_l[k] = {}
    for l in lower:
        cipher = chr((ord(l) - offset_lower + key_loc) % 26 + offset_lower)
        dicts_l[k][cipher] = l

# Diccionarios para las letras mayúsculas
dicts_u = {}
for k in key:
    key_loc = ord(k) - offset_upper
    dicts_u[k] = {}
    for u in upper:
        cipher = chr((ord(u) - offset_upper + key_loc) % 26 + offset_upper)
        dicts_u[k][cipher] = u

# Decodificación
count = 0
for c in instr:
    if c.isalpha():
        if c.islower():
            outstr += dicts_l[key[count % len(key)]][c]
        elif c.isupper():
            outstr += dicts_u[key[count % len(key)]][c]
        count += 1
    else:
        outstr += c

print(outstr)

```
## Notas Adicionales
creamos un solver.py para decodificar el texto que nos dan y posteriormente obtener la flag.
`picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_d85729g7}`
### Referencias
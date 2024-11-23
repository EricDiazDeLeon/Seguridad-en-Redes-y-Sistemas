## Objetivo
I just recently learnt about the SRA public key cryptosystem... or wait, was it supposed to be RSA? Hmmm, I should probably check...
Connect to the program on our server: nc saturn.picoctf.net 60141
Download the program: chal.py
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/SRA$ wget https://artifacts.picoctf.net/c/295/chal.py  
--2024-11-22 23:15:50--  https://artifacts.picoctf.net/c/295/chal.py  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:5800:16:5ec5:2840:93a1, 2600:9000:25ed:1800:16:5ec5:28  
40:93a1, 2600:9000:25ed:c200:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:5800:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 630 [application/octet-stream]  
Grabando a: «chal.py»  
  
chal.py                          100%[========================================================>]     630  --.-KB/s    en 0s         
  
2024-11-22 23:15:51 (9,52 MB/s) - «chal.py» guardado [630/630]  
  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/SRA$ la  
bash: la: orden no encontrada  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/SRA$ ls  
chal.py  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/SRA$ cat chal.py    
from Crypto.Util.number import getPrime, inverse, bytes_to_long  
from string import ascii_letters, digits  
from random import choice  
  
pride = "".join(choice(ascii_letters + digits) for _ in range(16))  
gluttony = getPrime(128)  
greed = getPrime(128)  
lust = gluttony * greed  
sloth = 65537  
envy = inverse(sloth, (gluttony - 1) * (greed - 1))  
  
anger = pow(bytes_to_long(pride.encode()), sloth, lust)  
  
print(f"{anger = }")  
print(f"{envy = }")  
  
print("vainglory?")  
vainglory = input("> ").strip()  
  
if vainglory == pride:  
   print("Conquered!")  
   with open("/challenge/flag.txt") as f:  
       print(f.read())  
else:  
   print("Hubris!")
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/SRA$ nc saturn.picoctf.net 60141
anger = 52190949931402773187978720055221310529666592180222471031618966392148685458708
envy = 6944124750369030851166178118880138127990803326767658085396230802627759519929
vainglory?
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/SRA$ python3 -m venv enviromentvirt
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/SRA$ source enviromentvirt/bin/activate
(enviromentvirt) (enviromentvirt) kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/SRA$ pip install pycryptodome  
Collecting pycryptodome  
 Downloading pycryptodome-3.21.0-cp36-abi3-manylinux_2_17_x86_64.manylinux2014_x86_64.whl.metadata (3.4 kB)  
Downloading pycryptodome-3.21.0-cp36-abi3-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (2.3 MB)  
  ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 2.3/2.3 MB 3.9 MB/s eta 0:00:00  
Installing collected packages: pycryptodome  
Successfully installed pycryptodome-3.21.0
(enviromentvirt) kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/SRA$ pip install sympy  
Collecting sympy  
 Downloading sympy-1.13.3-py3-none-any.whl.metadata (12 kB)  
Collecting mpmath<1.4,>=1.1.0 (from sympy)  
 Downloading mpmath-1.3.0-py3-none-any.whl.metadata (8.6 kB)  
Downloading sympy-1.13.3-py3-none-any.whl (6.2 MB)  
  ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 6.2/6.2 MB 5.1 MB/s eta 0:00:00  
Downloading mpmath-1.3.0-py3-none-any.whl (536 kB)  
  ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 536.2/536.2 kB 4.5 MB/s eta 0:00:00  
Installing collected packages: mpmath, sympy  
Successfully installed mpmath-1.3.0 sympy-1.13.3
(enviromentvirt) kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/SRA$ python3 solve.py    
[+] Opening connection to saturn.picoctf.net on port 60141: Done  
Factoring...  
[*] Switching to interactive mode  
gL2lWCoHAfzpF6Yv  
Conquered!  
picoCTF{7h053_51n5_4r3_n0_m0r3_2b7ad1ae}  
[*] Got EOF while reading in interactive  
$    
[*] Interrupted


```
## Notas Adicionales
usamos la biblioteca `pycryptodome` para crear un script para resolver el problema mediante fuerza bruta y encontrar la flag.
`picoCTF{7h053_51n5_4r3_n0_m0r3_2b7ad1ae}`
### Referencias
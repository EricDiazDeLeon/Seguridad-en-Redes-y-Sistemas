## Objetivo
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/38f30029ab93478310e906d3d084a4c1/values)
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act20$ wget https://mercury.picoctf.net/static/38f30029ab93478310e906d3d084a4c1/values  
--2024-10-23 10:28:47--  https://mercury.picoctf.net/static/38f30029ab93478310e906d3d084a4c1/values  
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142  
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 205 [application/octet-stream]  
Grabando a: «values»  
  
values                           100%[========================================================>]     205  --.-KB/s    en 0s         
  
2024-10-23 10:28:56 (99,1 MB/s) - «values» guardado [205/205]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act20$ ls  
values  
kali@KaliEND:~/Downloads/PicoCTF/Act20$ cat values    
Decrypt my super sick RSA:  
c: 240986837130071017759137533082982207147971245672412893755780400885108149004760496  
n: 831416828080417866340504968188990032810316193533653516022175784399720141076262857

kali@KaliEND:~/Downloads/PicoCTF/Act20$ python3
Python 3.12.6 (main, Sep  7 2024, 14:20:15) [GCC 14.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> c=240986837130071017759137533082982207147971245672412893755780400885108149004760496
>>> p=1593021310640923782355996681284584012117
>>> q=521911930824021492581321351826927897005221
>>> n=(p*q)
>>> n
831416828080417866340504968188990032810316193533653516022175784399720141076262857
>>> tn = (p-1) * (q-1)
>>> tn
831416828080417866340504968188990032809792688581518853605812107051211928595245520
>>> e = 65537
>>> d = pow(e, -1, tn)
>>> d
765055209030283349062826992563059537644801530091354135611213588168979150187907233
>>> m = pow (c, d, n)
>>> m
13016382529449106065927291425342535437996222135352905256639592405461024281868413
>>> bytes.fromhex(hex(m)[2:]).decode('utf-8')
'picoCTF{sma11_N_n0_g0od_23540368}'
>>> 

```
## Notas Adicionales
flag: `picoCTF{sma11_N_n0_g0od_23540368}`
### Referencias
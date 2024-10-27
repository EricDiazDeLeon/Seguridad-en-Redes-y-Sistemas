## Objetivo
Someone might have hidden the password in the trace file.Find the key to unlock [this file](https://artifacts.picoctf.net/c/493/flag.zip). [This tracefile](https://artifacts.picoctf.net/c/493/dump.pcap) might be good to analyze.
## Solución
cyberchef from hexadec, y from base64
```bash
This is the secret: picoCTF{R34DING_LOKd_
```

```bash
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_1$ wget https://artifacts.picoctf.net/c/493/flag.zip  
--2024-10-26 23:29:24--  https://artifacts.picoctf.net/c/493/flag.zip  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:2000:16:5ec5:2840:93a1, 2600:9000:25ed:e800:16:5ec5:28  
40:93a1, 2600:9000:25ed:ce00:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:2000:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 231 [application/octet-stream]  
Grabando a: «flag.zip»  
  
flag.zip                         100%[========================================================>]     231  --.-KB/s    en 0s         
  
2024-10-26 23:29:24 (114 MB/s) - «flag.zip» guardado [231/231]  
  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_1$ wget https://artifacts.picoctf.net/c/493/dump.pcap  
--2024-10-26 23:29:30--  https://artifacts.picoctf.net/c/493/dump.pcap  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:6c00:16:5ec5:2840:93a1, 2600:9000:25ed:a000:16:5ec5:28  
40:93a1, 2600:9000:25ed:bc00:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:6c00:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 7413 (7,2K) [application/octet-stream]  
Grabando a: «dump.pcap»  
  
dump.pcap                        100%[========================================================>]   7,24K  --.-KB/s    en 0s         
  
2024-10-26 23:29:31 (56,4 MB/s) - «dump.pcap» guardado [7413/7413]  
  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_1$ ls  
dump.pcap  flag.zip  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_1$ unzip flag.zip    
Archive:  flag.zip  
[flag.zip] flag password:    
extracting: flag                       
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_1$ ls  
dump.pcap  flag  flag.zip  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_1$ cat flag  
picoCTF{R34DING_LOKd_fil56_succ3ss_419835ef}
```
## Notas Adicionales
encontre la mitad de la flag en los datos de la pcap y despues de desencriptarla con cyberchef de hexadecimal y despues de base64 obtuve la mitad de la flag, despues segui buscando por que crei que ahi estaria la segunda mitad pero no, esta era la contrasena de el .zip asi que lo descomprimi y ahi estaba la flag completa:
`picoCTF{R34DING_LOKd_fil56_succ3ss_419835ef}`
### Referencias
cyberchef from hex y from base64
https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=NTY0NzY4NzA2Mzc5NDI3MDYzNzk0MjMwNjE0NzU1Njc2MzMyNTY2YTYzNmQ1NjMwNGY2OTQyNzc2MTU3NGU3NjUxMzE1MjQ3NjUzMTQ5N2E0ZTQ1NTI0YTU0NmI2NDY2NTQ0NTM5NGM1YTQ2MzgzZA
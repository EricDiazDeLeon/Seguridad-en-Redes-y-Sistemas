## Objetivo
Now you DON’T see me.This [report](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ wget https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf  
--2024-10-26 18:33:55--  https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:a200:16:5ec5:2840:93a1, 2600:9000:25ed:f200:16:5ec5:28  
40:93a1, 2600:9000:25ed:800:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:a200:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 34915 (34K) [application/octet-stream]  
Grabando a: «Financial_Report_for_ABC_Labs.pdf»  
  
Financial_Report_for_ABC_Labs.pd 100%[========================================================>]  34,10K  --.-KB/s    en 0s         
  
2024-10-26 18:33:56 (96,5 MB/s) - «Financial_Report_for_ABC_Labs.pdf» guardado [34915/34915]  
  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ ls  
Financial_Report_for_ABC_Labs.pdf
```
## Notas Adicionales
en el pdf se encuentra informacion confidencial, al verla esta negra, subrayada para que nadie lo pueda ver, pero se puede seleccionar con el cursor, al copiarla y pegarla encontramos la flag:
```bash
Financial Report for ABC Labs, Kigali, Rwanda for the year 2021. Breakdown - Just painted over in MS word. Cost Benefit Analysis Credit Debit This is not the flag, keep looking Expenses from the picoCTF{C4n_Y0u_S33_m3_fully} Redacted document.
``` 
### Referencias
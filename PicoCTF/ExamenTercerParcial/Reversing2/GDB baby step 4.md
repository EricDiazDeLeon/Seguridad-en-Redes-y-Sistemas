## Objetivo
`main` calls a function that multiplies `eax` by a constant. The flag for this challenge is that constant in decimal base. If the constant you find is 0x1000, the flag will be `picoCTF{4096}`.Debug [this](https://artifacts.picoctf.net/c/532/debugger0_d).
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/gdbbaby4$ wget https://artifacts.picoctf.net/c/532/debugger0_d  
--2024-11-23 00:10:20--  https://artifacts.picoctf.net/c/532/debugger0_d  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:1600:16:5ec5:2840:93a1, 2600:9000:25ed:de00:16:5ec5:28  
40:93a1, 2600:9000:25ed:5c00:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:1600:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 16328 (16K) [application/octet-stream]  
Grabando a: «debugger0_d»  
  
debugger0_d                      100%[========================================================>]  15,95K  --.-KB/s    en 0s         
  
2024-11-23 00:10:21 (80,0 MB/s) - «debugger0_d» guardado [16328/16328]  
  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/gdbbaby4$ ls  
debugger0_d  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/gdbbaby4$ chmod +x debugger0_d
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/gdbbaby4$ gdb --args ./debugger0_d  
GNU gdb (Debian 15.1-1) 15.1  
Copyright (C) 2024 Free Software Foundation, Inc.  
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>  
This is free software: you are free to change and redistribute it.  
There is NO WARRANTY, to the extent permitted by law.  
Type "show copying" and "show warranty" for details.  
This GDB was configured as "x86_64-linux-gnu".  
Type "show configuration" for configuration details.  
For bug reporting instructions, please see:  
<https://www.gnu.org/software/gdb/bugs/>.  
Find the GDB manual and other documentation resources online at:  
   <http://www.gnu.org/software/gdb/documentation/>.  
  
For help, type "help".  
Type "apropos word" to search for commands related to "word"...  
Reading symbols from ./debugger0_d...  
(No debugging symbols found in ./debugger0_d)  
(gdb) layout asm
(gdb) quit  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/gdbbaby4$ printf "picoCTF{%d}\n" 0x3269 | tee flag.txt  
picoCTF{12905}
```
## Notas Adicionales
`picoCTF{12905}`
### Referencias
## Objetivo
This program has constructed the flag using hex ascii values. Identify the flag text by disassembling the program.You can download the file from [here](https://artifacts.picoctf.net/c/508/asciiftw).
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/ASCIIFTW$ wget https://artifacts.picoctf.net/c/508/asciiftw  
--2024-11-22 23:30:21--  https://artifacts.picoctf.net/c/508/asciiftw  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:7600:16:5ec5:2840:93a1, 2600:9000:25ed:8600:16:5ec5:28  
40:93a1, 2600:9000:25ed:7400:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:7600:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 16752 (16K) [application/octet-stream]  
Grabando a: «asciiftw»  
  
asciiftw                         100%[========================================================>]  16,36K  --.-KB/s    en 0,006s     
  
2024-11-22 23:30:22 (2,53 MB/s) - «asciiftw» guardado [16752/16752]  
  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/ASCIIFTW$ ls  
asciiftw  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/ASCIIFTW$ file asciiftw    
asciiftw: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, Bu  
ildID[sha1]=e1c32dace8ac1516160b771e493f5ebffcac9855, for GNU/Linux 3.2.0, not stripped  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/ASCIIFTW$ chmod +x asciiftw    
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/ASCIIFTW$ ./asciiftw    
The flag starts with 70  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/ASCIIFTW$ gdb ./asciiftw  
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
Reading symbols from ./asciiftw...  
(No debugging symbols found in ./asciiftw)  
(gdb)
```
## Notas Adicionales
0x70 0x69 0x63 0x6f 0x43 0x54 0x46 0x7b 0x41 0x53 0x43 0x49 0x49 0x5f 0x49 0x53 0x5f 0x45 0x41 0x53 0x59 0x5f 0x38 0x39 0x36 0x30 0x46 0x30 0x41 0x46 0x7d converti de hex a:
flag: `picoCTF{ASCII_IS_EASY_8960F0AF}`
### Referencias
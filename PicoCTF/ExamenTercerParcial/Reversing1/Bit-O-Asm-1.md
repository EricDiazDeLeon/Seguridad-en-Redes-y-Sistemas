## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt).
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/bitO1$ wget https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt  
--2024-11-22 23:33:52--  https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:2e00:16:5ec5:2840:93a1, 2600:9000:25ed:4400:16:5ec5:28  
40:93a1, 2600:9000:25ed:3000:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:2e00:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 209 [application/octet-stream]  
Grabando a: «disassembler-dump0_a.txt»  
  
disassembler-dump0_a.txt         100%[========================================================>]     209  --.-KB/s    en 0s         
  
2024-11-22 23:33:53 (1,78 MB/s) - «disassembler-dump0_a.txt» guardado [209/209]  
  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/bitO1$ ls  
disassembler-dump0_a.txt  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/bitO1$ cat disassembler-dump0_a.txt    
<+0>:     endbr64    
<+4>:     push   rbp  
<+5>:     mov    rbp,rsp  
<+8>:     mov    DWORD PTR [rbp-0x4],edi  
<+11>:    mov    QWORD PTR [rbp-0x10],rsi  
<+15>:    mov    eax,0x30  
<+20>:    pop    rbp  
<+21>:    ret  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/bitO1$ python3  
Python 3.12.6 (main, Sep  7 2024, 14:20:15) [GCC 14.2.0] on linux  
Type "help", "copyright", "credits" or "license" for more information.  
>>> print("{:d}".format(0x30))  
48  
>>> picoCTF{48}             (:
```
## Notas Adicionales
`picoCTF{48}`
### Referencias
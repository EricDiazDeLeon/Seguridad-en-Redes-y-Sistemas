## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt).
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/bitO2$ wget https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt  
--2024-11-22 23:35:56--  https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:7a00:16:5ec5:2840:93a1, 2600:9000:25ed:8a00:16:5ec5:28  
40:93a1, 2600:9000:25ed:e800:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:7a00:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 270 [application/octet-stream]  
Grabando a: «disassembler-dump0_b.txt»  
  
disassembler-dump0_b.txt         100%[========================================================>]     270  --.-KB/s    en 0s         
  
2024-11-22 23:35:57 (140 MB/s) - «disassembler-dump0_b.txt» guardado [270/270]  
  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/bitO2$ ls  
disassembler-dump0_b.txt  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/bitO2$ cat disassembler-dump0_b.txt    
<+0>:     endbr64    
<+4>:     push   rbp  
<+5>:     mov    rbp,rsp  
<+8>:     mov    DWORD PTR [rbp-0x14],edi  
<+11>:    mov    QWORD PTR [rbp-0x20],rsi  
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a  
<+22>:    mov    eax,DWORD PTR [rbp-0x4]  
<+25>:    pop    rbp  
<+26>:    ret
```
## Notas Adicionales
en la linea <+15> vemos una DWORD que es:
`0x9fe1a` en hexadecimal equivale a `654874` en decimal 654874
`picoCTF{654874}`
### Referencias
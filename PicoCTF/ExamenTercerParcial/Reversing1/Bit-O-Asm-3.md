## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt).
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/bitO3$ wget https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt  
--2024-11-22 23:38:18--  https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:7e00:16:5ec5:2840:93a1, 2600:9000:25ed:f000:16:5ec5:28  
40:93a1, 2600:9000:25ed:8600:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:7e00:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 461 [application/octet-stream]  
Grabando a: «disassembler-dump0_c.txt»  
  
disassembler-dump0_c.txt         100%[========================================================>]     461  --.-KB/s    en 0s         
  
2024-11-22 23:38:19 (3,25 MB/s) - «disassembler-dump0_c.txt» guardado [461/461]  
  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/bitO3$ ls  
disassembler-dump0_c.txt  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/bitO3$ cat disassembler-dump0_c.txt    
<+0>:     endbr64    
<+4>:     push   rbp  
<+5>:     mov    rbp,rsp  
<+8>:     mov    DWORD PTR [rbp-0x14],edi  
<+11>:    mov    QWORD PTR [rbp-0x20],rsi  
<+15>:    mov    DWORD PTR [rbp-0xc],0x9fe1a  
<+22>:    mov    DWORD PTR [rbp-0x8],0x4  
<+29>:    mov    eax,DWORD PTR [rbp-0xc]  
<+32>:    imul   eax,DWORD PTR [rbp-0x8]  
<+36>:    add    eax,0x1f5  
<+41>:    mov    DWORD PTR [rbp-0x4],eax  
<+44>:    mov    eax,DWORD PTR [rbp-0x4]  
<+47>:    pop    rbp  
<+48>:    ret  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/bitO3$
```
## Notas Adicionales
1. **<+15>:** Se almacena el valor DWORD `654874` en la ubicación de memoria apuntada por `[rbp-0xc]`.
2. **<+22>:** Se almacena el valor DWORD `4` en la ubicación de memoria apuntada por `[rbp-0x8]`.
3. **<+29>:** El valor almacenado en la ubicación de memoria apuntada por `[rbp-0xc]` (`654874`) se almacena en el registro `eax`.
4. **<+32>:** El valor almacenado en el registro `eax` se multiplica por el valor almacenado en la ubicación de memoria apuntada por `[rbp-0x8]` (`4`), y el resultado se almacena en el registro `eax`.
5. **<+36>:** Se suma `501` al valor almacenado en el registro `eax`, y el resultado se almacena nuevamente en el registro `eax`.
6. **<+41>:** El valor almacenado en el registro `eax` se guarda en la ubicación de memoria apuntada por `[rbp-0x4]`.
7. **<+44>:** El valor de la ubicación de memoria apuntada por `[rbp-0x4]` se almacena en el registro `eax`.

`picoCTF{2619997}`
### Referencias
## Objetivo
We have recovered a [binary](https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680ea5b9ddf/rev) and a [text file](https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680ea5b9ddf/rev_this). Can you reverse the flag.
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act23/reverse_Cipher$ wget https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680  
ea5b9ddf/rev  
--2024-11-06 11:18:14--  https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680ea5b9ddf/rev  
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8  
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 16856 (16K) [application/octet-stream]  
Grabando a: «rev»  
  
rev                              100%[========================================================>]  16,46K  --.-KB/s    en 0s         
  
2024-11-06 11:18:22 (79,1 MB/s) - «rev» guardado [16856/16856]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act23/reverse_Cipher$ wget https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680  
ea5b9ddf/rev_this  
--2024-11-06 11:18:29--  https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680ea5b9ddf/rev_this  
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8  
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 24 [application/octet-stream]  
Grabando a: «rev_this»  
  
rev_this                         100%[========================================================>]      24  --.-KB/s    en 0s         
  
2024-11-06 11:18:39 (12,8 MB/s) - «rev_this» guardado [24/24]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act23/reverse_Cipher$ ls  
rev  rev_this  
kali@KaliEND:~/Downloads/PicoCTF/Act23/reverse_Cipher$ file rev_this    
rev_this: ASCII text, with no line terminators  
kali@KaliEND:~/Downloads/PicoCTF/Act23/reverse_Cipher$ cat rev_this    
picoCTF{w1{1wq8/7376j.:}kali@KaliEND:~/Downloads/PicoCTF/Act23/reverse_Cipher$ file rev  
rev: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU  
/Linux 3.2.0, BuildID[sha1]=523d51973c11197605c76f84d4afb0fe9e59338c, not stripped
kali@KaliEND:~/Downloads/PicoCTF/Act23/reverse_Cipher$ gdb rev  
GNU gdb (Debian 15.1-1) 15.1  
Copyright (C) 2024 Free Software Foundation, Inc.  
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/lice  
nses/gpl.html>  
This is free software: you are free to change and redistribute  
it.  
There is NO WARRANTY, to the extent permitted by law.  
Type "show copying" and "show warranty" for details.  
This GDB was configured as "x86_64-linux-gnu".  
Type "show configuration" for configuration details.  
For bug reporting instructions, please see:  
<https://www.gnu.org/software/gdb/bugs/>.  
Find the GDB manual and other documentation resources online at  
:  
   <http://www.gnu.org/software/gdb/documentation/>.  
  
For help, type "help".  
Type "apropos word" to search for commands related to "word"...  
Reading symbols from rev...  
(No debugging symbols found in rev)  
(gdb) disassemble main  
Dump of assembler code for function main:  
  0x0000000000001185 <+0>:     push   %rbp  
  0x0000000000001186 <+1>:     mov    %rsp,%rbp  
  0x0000000000001189 <+4>:     sub    $0x50,%rsp  
  0x000000000000118d <+8>:     lea    0xe74(%rip),%rsi          
# 0x2008  
  0x0000000000001194 <+15>:    lea    0xe6f(%rip),%rdi          
# 0x200a  
  0x000000000000119b <+22>:    call   0x1070 <fopen@plt>  
  0x00000000000011a0 <+27>:    mov    %rax,-0x18(%rbp)  
  0x00000000000011a4 <+31>:    lea    0xe68(%rip),%rsi          
# 0x2013  
  0x00000000000011ab <+38>:    lea    0xe63(%rip),%rdi          
# 0x2015  
  0x00000000000011b2 <+45>:    call   0x1070 <fopen@plt>  
  0x00000000000011b7 <+50>:    mov    %rax,-0x20(%rbp)  
  0x00000000000011bb <+54>:    cmpq   $0x0,-0x18(%rbp)  
  0x00000000000011c0 <+59>:    jne    0x11ce <main+73>  
  0x00000000000011c2 <+61>:    lea    0xe57(%rip),%rdi          
# 0x2020  
  0x00000000000011c9 <+68>:    call   0x1030 <puts@plt>  
  0x00000000000011ce <+73>:    cmpq   $0x0,-0x20(%rbp)  
  0x00000000000011d3 <+78>:    jne    0x11e1 <main+92>  
  0x00000000000011d5 <+80>:    lea    0xe7e(%rip),%rdi          
# 0x205a  
  0x00000000000011dc <+87>:    call   0x1030 <puts@plt>  
  0x00000000000011e1 <+92>:    mov    -0x18(%rbp),%rdx  
  0x00000000000011e5 <+96>:    lea    -0x50(%rbp),%rax  
  0x00000000000011e9 <+100>:   mov    %rdx,%rcx  
  0x00000000000011ec <+103>:   mov    $0x1,%edx  
  0x00000000000011f1 <+108>:   mov    $0x18,%esi  
  0x00000000000011f6 <+113>:   mov    %rax,%rdi  
  0x00000000000011f9 <+116>:   call   0x1040 <fread@plt>  
--Type <RET> for more, q to quit, c to continue without paging-  
-set disassembly-flavor intel  
  0x00000000000011fe <+121>:   mov    %eax,-0x24(%rbp)  
  0x0000000000001201 <+124>:   cmpl   $0x0,-0x24(%rbp)  
  0x0000000000001205 <+128>:   jg     0x1211 <main+140>  
  0x0000000000001207 <+130>:   mov    $0x0,%edi  
  0x000000000000120c <+135>:   call   0x1080 <exit@plt>  
  0x0000000000001211 <+140>:   movl   $0x0,-0x8(%rbp)  
  0x0000000000001218 <+147>:   jmp    0x123d <main+184>  
  0x000000000000121a <+149>:   mov    -0x8(%rbp),%eax  
  0x000000000000121d <+152>:   cltq  
  0x000000000000121f <+154>:   movzbl -0x50(%rbp,%rax,1),%eax  
  0x0000000000001224 <+159>:   mov    %al,-0x1(%rbp)  
  0x0000000000001227 <+162>:   movsbl -0x1(%rbp),%eax  
  0x000000000000122b <+166>:   mov    -0x20(%rbp),%rdx  
  0x000000000000122f <+170>:   mov    %rdx,%rsi  
  0x0000000000001232 <+173>:   mov    %eax,%edi  
  0x0000000000001234 <+175>:   call   0x1060 <fputc@plt>  
  0x0000000000001239 <+180>:   addl   $0x1,-0x8(%rbp)  
  0x000000000000123d <+184>:   cmpl   $0x7,-0x8(%rbp)  
  0x0000000000001241 <+188>:   jle    0x121a <main+149>  
  0x0000000000001243 <+190>:   movl   $0x8,-0xc(%rbp)  
  0x000000000000124a <+197>:   jmp    0x128f <main+266>  
  0x000000000000124c <+199>:   mov    -0xc(%rbp),%eax  
  0x000000000000124f <+202>:   cltq  
  0x0000000000001251 <+204>:   movzbl -0x50(%rbp,%rax,1),%eax  
  0x0000000000001256 <+209>:   mov    %al,-0x1(%rbp)  
  0x0000000000001259 <+212>:   mov    -0xc(%rbp),%eax  
  0x000000000000125c <+215>:   and    $0x1,%eax  
--Type <RET> for more, q to quit, c to contic  
  0x000000000000125f <+218>:   test   %eax,%eax  
  0x0000000000001261 <+220>:   jne    0x126f <main+234>  
  0x0000000000001263 <+222>:   movzbl -0x1(%rbp),%eax  
  0x0000000000001267 <+226>:   add    $0x5,%eax  
  0x000000000000126a <+229>:   mov    %al,-0x1(%rbp)  
  0x000000000000126d <+232>:   jmp    0x1279 <main+244>  
  0x000000000000126f <+234>:   movzbl -0x1(%rbp),%eax  
  0x0000000000001273 <+238>:   sub    $0x2,%eax  
  0x0000000000001276 <+241>:   mov    %al,-0x1(%rbp)  
  0x0000000000001279 <+244>:   movsbl -0x1(%rbp),%eax  
  0x000000000000127d <+248>:   mov    -0x20(%rbp),%rdx  
  0x0000000000001281 <+252>:   mov    %rdx,%rsi  
  0x0000000000001284 <+255>:   mov    %eax,%edi  
  0x0000000000001286 <+257>:   call   0x1060 <fputc@plt>  
  0x000000000000128b <+262>:   addl   $0x1,-0xc(%rbp)  
  0x000000000000128f <+266>:   cmpl   $0x16,-0xc(%rbp)  
  0x0000000000001293 <+270>:   jle    0x124c <main+199>  
  0x0000000000001295 <+272>:   movzbl -0x39(%rbp),%eax  
  0x0000000000001299 <+276>:   mov    %al,-0x1(%rbp)  
  0x000000000000129c <+279>:   movsbl -0x1(%rbp),%eax  
  0x00000000000012a0 <+283>:   mov    -0x20(%rbp),%rdx  
  0x00000000000012a4 <+287>:   mov    %rdx,%rsi  
  0x00000000000012a7 <+290>:   mov    %eax,%edi  
  0x00000000000012a9 <+292>:   call   0x1060 <fputc@plt>  
  0x00000000000012ae <+297>:   mov    -0x20(%rbp),%rax  
  0x00000000000012b2 <+301>:   mov    %rax,%rdi  
  0x00000000000012b5 <+304>:   call   0x1050 <fclose@plt>  
  0x00000000000012ba <+309>:   mov    -0x18(%rbp),%rax  
  0x00000000000012be <+313>:   mov    %rax,%rdi  
  0x00000000000012c1 <+316>:   call   0x1050 <fclose@plt>  
  0x00000000000012c6 <+321>:   nop  
  0x00000000000012c7 <+322>:   leave  
  0x00000000000012c8 <+323>:   ret  
End of assembler dump.  
(gdb) quit
```
solve.py:
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act23/reverse_Cipher$ nano sol  
ve.py    
kali@KaliEND:~/Downloads/PicoCTF/Act23/reverse_Cipher$ cat solv  
e.py    
rev = open ('rev_this').read()  
flag = ''  
  
for i in range(0):  
       flag += rev[i]  
  
for j in range(8,24):  
       if j&1 == 0:  
               flag += chr( ord(rev[j]) - 5)  
       else:  
               flag += chr( ord(rev[j]) + 2)  
flag += rev[23]  
print(flag)  
kali@KaliEND:~/Downloads/PicoCTF/Act23/reverse_Cipher$ python3  
solve.py    
r3v3rs312528e05}
```
## Notas Adicionales
usamos ghidra para ver el codigo de una manera mas legible y despues creamos un archivo en python para hacer exactamente lo contrario y ejecutando dicho programa encontramos la flag:
`r3v3rs312528e05}`
solo falta ponerle el formato correspondiente:
`picoCTF{r3v3rs312528e05}`
### Referencias
ghidra:
https://ghidra-sre.org/
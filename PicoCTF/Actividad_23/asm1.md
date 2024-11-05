## Objetivo
What does asm1(0x6fa) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/b41e08fc19ceb9d0466ebd68d36c5630/test.S)
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act23$ wget https://jupiter.challenges.picoctf.org/static/b41e08fc19ceb9d0466ebd68d36c5630/test.S  
--2024-11-04 10:32:46--  https://jupiter.challenges.picoctf.org/static/b41e08fc19ceb9d0466ebd68d36c5630/test.S  
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8  
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 642 [application/octet-stream]  
Grabando a: «test.S»  
  
test.S                           100%[========================================================>]     642  --.-KB/s    en 0s         
  
2024-11-04 10:32:55 (7,78 MB/s) - «test.S» guardado [642/642]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ ls  
test.S  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ file test.S    
test.S: ASCII text  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ cat test.S    
asm1:  
       <+0>:   push   ebp  
       <+1>:   mov    ebp,esp  
       <+3>:   cmp    DWORD PTR [ebp+0x8],0x3a2  
       <+10>:  jg     0x512 <asm1+37>  
       <+12>:  cmp    DWORD PTR [ebp+0x8],0x358  
       <+19>:  jne    0x50a <asm1+29>  
       <+21>:  mov    eax,DWORD PTR [ebp+0x8]  
       <+24>:  add    eax,0x12  
       <+27>:  jmp    0x529 <asm1+60>  
       <+29>:  mov    eax,DWORD PTR [ebp+0x8]  
       <+32>:  sub    eax,0x12  
       <+35>:  jmp    0x529 <asm1+60>  
       <+37>:  cmp    DWORD PTR [ebp+0x8],0x6fa  
       <+44>:  jne    0x523 <asm1+54>  
       <+46>:  mov    eax,DWORD PTR [ebp+0x8]  
       <+49>:  sub    eax,0x12  
       <+52>:  jmp    0x529 <asm1+60>  
       <+54>:  mov    eax,DWORD PTR [ebp+0x8]  
       <+57>:  add    eax,0x12  
       <+60>:  pop    ebp  
       <+61>:  ret
```
## Notas Adicionales
`0x6e8`
### Referencias
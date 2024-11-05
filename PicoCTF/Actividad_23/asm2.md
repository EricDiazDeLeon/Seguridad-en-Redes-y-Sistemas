## Objetivo
What does asm2(0xb,0x2e) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/717467c8c8b4332ea5873ad8fe7b2dad/test.S)
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act23$ wget https://jupiter.challenges.picoctf.org/static/717467c8c8b4332ea5873ad8fe7b2dad/test.S  
--2024-11-04 11:06:42--  https://jupiter.challenges.picoctf.org/static/717467c8c8b4332ea5873ad8fe7b2dad/test.S  
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8  
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 484 [application/octet-stream]  
Grabando a: «test.S»  
  
test.S                           100%[========================================================>]     484  --.-KB/s    en 0s         
  
2024-11-04 11:06:50 (10,8 MB/s) - «test.S» guardado [484/484]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ lx  
bash: lx: orden no encontrada  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ ls  
test.S  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ cat test.S    
asm2:  
       <+0>:   push   ebp  
       <+1>:   mov    ebp,esp  
       <+3>:   sub    esp,0x10  
       <+6>:   mov    eax,DWORD PTR [ebp+0xc]  
       <+9>:   mov    DWORD PTR [ebp-0x4],eax  
       <+12>:  mov    eax,DWORD PTR [ebp+0x8]  
       <+15>:  mov    DWORD PTR [ebp-0x8],eax  
       <+18>:  jmp    0x509 <asm2+28>  
       <+20>:  add    DWORD PTR [ebp-0x4],0x1  
       <+24>:  sub    DWORD PTR [ebp-0x8],0xffffff80  
       <+28>:  cmp    DWORD PTR [ebp-0x8],0x63f3  
       <+35>:  jle    0x501 <asm2+20>  
       <+37>:  mov    eax,DWORD PTR [ebp-0x4]  
       <+40>:  leave     
       <+41>:  ret       
  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ nano test.S
kali@KaliEND:~/Downloads/PicoCTF/Act23$ nano test.S    
kali@KaliEND:~/Downloads/PicoCTF/Act23$ nano test.S    
kali@KaliEND:~/Downloads/PicoCTF/Act23$ nano test.S    
kali@KaliEND:~/Downloads/PicoCTF/Act23$ cat test.S    
stack  
[    ] c esp  
[    ] ebp - 0xc  
[0xb ] ebg - 0x8 - local2  
[0x2e] ebp - 0x4 - local1  
[ebp ] c ebp  
[ret ] ebp + 0x4  
[0xb ] ebp + 0x8  
[0x2e] epb + 0xc  
  
[ 0xb     ] eax  
  
asm2(0xb,0x2e):  
       <+0>:   push   ebp  
       <+1>:   mov    ebp,esp  
       <+3>:   sub    esp,0x10  
       <+6>:   mov    eax,DWORD PTR [ebp+0xc]  
       <+9>:   mov    DWORD PTR [ebp-0x4],eax  
       <+12>:  mov    eax,DWORD PTR [ebp+0x8]  
       <+15>:  mov    DWORD PTR [ebp-0x8],eax  
       <+18>:  jmp    0x509 <asm2+28>  
       <+20>:  add    DWORD PTR [ebp-0x4],0x1  
       <+24>:  sub    DWORD PTR [ebp-0x8],0xffffff80  
       <+28>:  cmp    DWORD PTR [ebp-0x8],0x63f3  
       <+35>:  jle    0x501 <asm2+20>  
       <+37>:  mov    eax,DWORD PTR [ebp-0x4]  
       <+40>:  leave     
       <+41>:  ret
```
## Notas Adicionales
flag: `0xf6`
### Referencias
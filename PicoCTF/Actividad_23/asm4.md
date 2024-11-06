## Objetivo
What will asm4("picoCTF_a3112") return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/80186ad81f4a1569b480e7fbf68b29ca/test.S)
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act23$ wget https://jupiter.challenges.picoctf.org/static/80186ad81f4a1569b480e7fbf68b29ca/test.S  
--2024-11-06 10:17:52--  https://jupiter.challenges.picoctf.org/static/80186ad81f4a1569b480e7fbf68b29ca/test.S  
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8  
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 1743 (1,7K) [application/octet-stream]  
Grabando a: «test.S»  
  
test.S                           100%[========================================================>]   1,70K  --.-KB/s    en 0s         
  
2024-11-06 10:18:01 (29,4 MB/s) - «test.S» guardado [1743/1743]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ ls  
test.S  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ cat test.S    
asm4:  
       <+0>:   push   ebp  
       <+1>:   mov    ebp,esp  
       <+3>:   push   ebx  
       <+4>:   sub    esp,0x10  
       <+7>:   mov    DWORD PTR [ebp-0x10],0x246  
       <+14>:  mov    DWORD PTR [ebp-0xc],0x0  
       <+21>:  jmp    0x518 <asm4+27>  
       <+23>:  add    DWORD PTR [ebp-0xc],0x1  
       <+27>:  mov    edx,DWORD PTR [ebp-0xc]  
       <+30>:  mov    eax,DWORD PTR [ebp+0x8]  
       <+33>:  add    eax,edx  
       <+35>:  movzx  eax,BYTE PTR [eax]  
       <+38>:  test   al,al  
       <+40>:  jne    0x514 <asm4+23>  
       <+42>:  mov    DWORD PTR [ebp-0x8],0x1  
       <+49>:  jmp    0x587 <asm4+138>  
       <+51>:  mov    edx,DWORD PTR [ebp-0x8]  
       <+54>:  mov    eax,DWORD PTR [ebp+0x8]  
       <+57>:  add    eax,edx  
       <+59>:  movzx  eax,BYTE PTR [eax]  
       <+62>:  movsx  edx,al  
       <+65>:  mov    eax,DWORD PTR [ebp-0x8]  
       <+68>:  lea    ecx,[eax-0x1]  
       <+71>:  mov    eax,DWORD PTR [ebp+0x8]  
       <+74>:  add    eax,ecx  
       <+76>:  movzx  eax,BYTE PTR [eax]  
       <+79>:  movsx  eax,al  
       <+82>:  sub    edx,eax  
       <+84>:  mov    eax,edx  
       <+86>:  mov    edx,eax  
       <+88>:  mov    eax,DWORD PTR [ebp-0x10]  
       <+91>:  lea    ebx,[edx+eax*1]  
       <+94>:  mov    eax,DWORD PTR [ebp-0x8]  
       <+97>:  lea    edx,[eax+0x1]  
       <+100>: mov    eax,DWORD PTR [ebp+0x8]  
       <+103>: add    eax,edx  
       <+105>: movzx  eax,BYTE PTR [eax]  
       <+108>: movsx  edx,al  
       <+111>: mov    ecx,DWORD PTR [ebp-0x8]  
       <+114>: mov    eax,DWORD PTR [ebp+0x8]  
       <+117>: add    eax,ecx  
       <+119>: movzx  eax,BYTE PTR [eax]  
       <+122>: movsx  eax,al  
       <+125>: sub    edx,eax  
       <+127>: mov    eax,edx  
       <+129>: add    eax,ebx  
       <+131>: mov    DWORD PTR [ebp-0x10],eax  
       <+134>: add    DWORD PTR [ebp-0x8],0x1  
       <+138>: mov    eax,DWORD PTR [ebp-0xc]  
       <+141>: sub    eax,0x1  
       <+144>: cmp    DWORD PTR [ebp-0x8],eax  
       <+147>: jl     0x530 <asm4+51>  
       <+149>: mov    eax,DWORD PTR [ebp-0x10]  
       <+152>: add    esp,0x10  
       <+155>: pop    ebx  
       <+156>: pop    ebp  
       <+157>: ret
kali@KaliEND:~/Downloads/PicoCTF/Act23$ ls  
test.S  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ cat test.S | cut -d ":" -f 2 > chal.s  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ ls  
chal.s  test.S  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ nano chal.s    
kali@KaliEND:~/Downloads/PicoCTF/Act23$ nano chal.s
kali@KaliEND:~/Downloads/PicoCTF/Act23$ gcc -m32 -c chal.s -o chal.o  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ ls  
chal.o  chal.s  test.S  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ file chal.o  
chal.o: ELF 32-bit LSB relocatable, Intel 80386, version 1 (SYSV), not stripped  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ chmod -x chal.o  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ ./chal.o  
bash: ./chal.o: Permiso denegado  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ chmod 777 chal.o  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ ./chal.o  
bash: ./chal.o: no se puede ejecutar fichero binario: Formato de ejecutable incorrecto

kali@KaliEND:~/Downloads/PicoCTF/Act23$ gcc -m32 -c solve.c -o solve.o -w  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ ls  
asm4  chal.o  chal.s  cracked  gdbme  need-for-speed  reverse_Cipher  reverse_Cypher  solve.c  solve.o  test.S  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ gcc -m32 -o a.out solve.o chal.o  
/usr/bin/ld: aviso: chal.o: que falte la sección .note.GNU-stack implica una pila ejecutable  
/usr/bin/ld: NOTA: Este comportamiento está obsoleto y se eliminará en una versión futura del enlazador  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ ls  
a.out  asm4  chal.o  chal.s  cracked  gdbme  need-for-speed  reverse_Cipher  reverse_Cypher  solve.c  solve.o  test.S  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ ./a.out  
Flag: 0x1d0

```
## Notas Adicionales
el programa que creamos en lenguaje c invoca la funcion asm4 en lenguaje ensamblador y le pasa el parametro `"picoCTF_a3112"` y se ejecuta el programa en ensamblador regresando en el registro de memoria EAX la flag.
flag: `0x1d0`
### Referencias
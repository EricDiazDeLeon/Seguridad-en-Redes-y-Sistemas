## Objetivo
What does asm3(0xd73346ed,0xd48672ae,0xd3c8b139) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/17c5620fcffa388fe518d31cb4dd99a0/test.S)
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act23$ wget https://jupiter.challenges.picoctf.org/static/17c5620fcffa388fe518d31cb4dd99a0/test.S  
--2024-11-04 11:31:37--  https://jupiter.challenges.picoctf.org/static/17c5620fcffa388fe518d31cb4dd99a0/test.S  
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8  
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 286 [application/octet-stream]  
Grabando a: «test.S»  
  
test.S                           100%[========================================================>]     286  --.-KB/s    en 0s         
  
2024-11-04 11:31:45 (4,56 MB/s) - «test.S» guardado [286/286]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ ls  
test.S
```
## Notas Adicionales
ejecutamos el codigo usando un programa de emulacion de ensamblador ordenando los parametros de las funciones al revez, las ultimas primero.
```bash
push 0xd3c8b139	
push 0xd48672ae
push 0xd73346ed
call asm3
	
asm3:
		push   ebp
        mov    ebp,esp
        xor    eax,eax
        mov    ah,BYTE PTR [ebp+0xa]
        shl    ax,0x10
        sub    al,BYTE PTR [ebp+0xc]
        add    ah,BYTE PTR [ebp+0xd]
        xor    ax,WORD PTR [ebp+0x10]
        nop
        pop    ebp
        ret
```
despues observamos la window de Registros y vemos el campo EAX:
`0x0000C36B`
flag:`0xC36B`
### Referencias
x86 assembly emulator
https://carlosrafaelgn.com.br/Asm86/
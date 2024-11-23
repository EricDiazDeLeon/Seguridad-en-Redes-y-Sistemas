## Objetivo
I wonder what this really is... [enc](https://mercury.picoctf.net/static/0d3145dafdc4fbcf01891912eb6c0968/enc) `''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])`
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/transformat$ wget https://mercury.picoctf.net/static/0d3145dafdc4fbcf01891912eb6c0  
968/enc  
--2024-11-22 23:55:53--  https://mercury.picoctf.net/static/0d3145dafdc4fbcf01891912eb6c0968/enc  
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142  
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 57 [application/octet-stream]  
Grabando a: «enc»  
  
enc                              100%[========================================================>]      57  --.-KB/s    en 0s         
  
2024-11-22 23:55:53 (24,3 MB/s) - «enc» guardado [57/57]  
  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/transformat$ ls  
enc  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/transformat$ file enc    
enc: Unicode text, UTF-8 text, with no line terminators  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/transformat$ cat enc    
灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸弲㘶㠴挲ぽkali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/transformat$ nano solve.py  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/transformat$ python3 solve.py    
Flag: picoCTF{16_bits_inst34d_of_8_26684c20}
```
## Notas Adicionales

### Referencias
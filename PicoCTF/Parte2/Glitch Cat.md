## Objetivo 
Our flag printing service has started glitching!

Additional details will be available after launching your challenge instance.
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/parte2$ nc saturn.picoctf.net 49632  
'picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) +  
chr(0x65) + '}'  
kali@KaliEND:~/Downloads/PicoCTF/parte2$
```
## Notas Adicionales 
use cyberchef para decodificar cada letra.
- `chr(0x61)` = 'a'
- `chr(0x34)` = '4'
- `chr(0x33)` = '3'
- `chr(0x39)` = '9'
- `chr(0x32)` = '2'
- `chr(0x64)` = 'd'
- `chr(0x32)` = '2'
- `chr(0x65)` = 'e'

picoCTF{gl17ch_m3_n07_a4392d2e}
### Referencias


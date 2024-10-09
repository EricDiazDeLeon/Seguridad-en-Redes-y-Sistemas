## Objetivo 
I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://jupiter.challenges.picoctf.org/static/74274b96fe966126a1953c80762af80d/whitepages.txt) is all blank!
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act15$ wget https://jupiter.challenges.picoctf.org/static/74274b96fe966126a1953c80762af80d/whitep  
ages.txt  
--2024-10-07 10:39:25--  https://jupiter.challenges.picoctf.org/static/74274b96fe966126a1953c80762af80d/whitepages.txt  
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8  
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 2964 (2,9K) [application/octet-stream]  
Grabando a: «whitepages.txt»  
  
whitepages.txt                   100%[========================================================>]   2,89K  --.-KB/s    en 0s         
  
2024-10-07 10:39:28 (36,2 MB/s) - «whitepages.txt» guardado [2964/2964]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act15$ ls  
message.wav  sstv  whitepages.txt  
kali@KaliEND:~/Downloads/PicoCTF/Act15$ cat whitepages.txt    
                                                                                                                                    
                                                                                                                                    
                                                                                                                                    
                                                                                                                                    
                                                                                                                                    
                                                                                                                                   
                                                                                                                                    
                                                                                                                                    
                                                                                                                                    
                                                                                                                                   
                                                                            kali@KaliEND:~/Downloads/PicoCTF/Act15$
kali@KaliEND:~/Downloads/PicoCTF/Act15$ xxd -l 30 whitepages.txt    
00000000: e280 83e2 8083 e280 83e2 8083 20e2 8083  ............ ...  
00000010: 20e2 8083 e280 83e2 8083 e280 83e2        .............  
kali@KaliEND:~/Downloads/PicoCTF/Act15$                                                                     
```
cambiamos los espacios por ceros y el simbolo en blanco que queda en unos:
```
0000101000001001000010010111000001101001011000110110111101000011010101000100011000001010000010100000100100001001010100110100010101000101001000000101000001010101010000100100110001001001010000110010000001010010010001010100001101001111010100100100010001010011001000000010011000100000010000100100000101000011010010110100011101010010010011110101010101001110010001000010000001010010010001010101000001001111010100100101010000001010000010010000100100110101001100000011000000110000001000000100011001101111011100100110001001100101011100110010000001000001011101100110010100101100001000000101000001101001011101000111010001110011011000100111010101110010011001110110100000101100001000000101000001000001001000000011000100110101001100100011000100110011000010100000100100001001011100000110100101100011011011110100001101010100010001100111101101101110011011110111010001011111011000010110110001101100010111110111001101110000011000010110001101100101011100110101111101100001011100100110010101011111011000110111001001100101011000010111010001100101011001000101111101100101011100010111010101100001011011000101111101100011001101010011010001100110001100100011011101100011011001000011000000110101011000110011001000110001001110000011100101100110001110000011000100110100001101110110001101100011001101100110011000110101011001000110010101100010001100100110010100110101001101100111110100001010000010010000100

```
Lo metemos en cyberchef:
```

		picoCTF

		SEE PUBLIC RECORDS & BACKGROUND REPORT
		5000 Forbes Ave, Pittsburgh, PA 15213
		picoCTF{not_all_spaces_are_created_equal_c54f27cd05c2189f8147cc6f5deb2e56}
```
## Notas Adicionales 
Al descargar el archivo y hacerle un cat nos damos cuenta de que esta vacio, o eso creemos, pero no esta vacio, sino que es una convinacion de espacios y un caracter ascii invisible, entonces sustituimos los espacios por ceros y el otro simbolo en unos y asi obtenemos una cadena en binario, la traducimos y obtemenos la flag.
### Referencias
cyberchef
https://gchq.github.io/CyberChef/#recipe=From_Binary('Space',8)
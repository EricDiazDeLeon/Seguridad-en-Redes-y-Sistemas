## Objetivo
Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/e5825f58ef798fdd1af3f6013592a971/cat.jpg)
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Examen2$ wget https://mercury.picoctf.net/static/e5825f58ef798fdd1af3f6013592a971/cat.jpg  
--2024-10-26 16:58:52--  https://mercury.picoctf.net/static/e5825f58ef798fdd1af3f6013592a971/cat.jpg  
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142  
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 878136 (858K) [application/octet-stream]  
Grabando a: «cat.jpg»  
  
cat.jpg                          100%[========================================================>] 857,55K   392KB/s    en 2,2s       
  
2024-10-26 16:58:56 (392 KB/s) - «cat.jpg» guardado [878136/878136]  
  
kali@KaliEND:~/Downloads/PicoCTF/Examen2$ ls  
cat.jpg
kali@KaliEND:~/Downloads/PicoCTF/Examen2$ strings cat.jpg | grep pico  
kali@KaliEND:~/Downloads/PicoCTF/Examen2$ eog cat.jpg    
kali@KaliEND:~/Downloads/PicoCTF/Examen2$ exiftool cat.jpg    
ExifTool Version Number         : 12.76  
File Name                       : cat.jpg  
Directory                       : .  
File Size                       : 878 kB  
File Modification Date/Time     : 2021:03:15 12:24:46-06:00  
File Access Date/Time           : 2024:10:26 17:02:50-06:00  
File Inode Change Date/Time     : 2024:10:26 16:58:56-06:00  
File Permissions                : -rw-rw-r--  
File Type                       : JPEG  
File Type Extension             : jpg  
MIME Type                       : image/jpeg  
JFIF Version                    : 1.02  
Resolution Unit                 : None  
X Resolution                    : 1  
Y Resolution                    : 1  
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617  
Copyright Notice                : PicoCTF  
Application Record Version      : 4  
XMP Toolkit                     : Image::ExifTool 10.80  
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9  
Rights                          : PicoCTF  
Image Width                     : 2560  
Image Height                    : 1598  
Encoding Process                : Baseline DCT, Huffman coding  
Bits Per Sample                 : 8  
Color Components                : 3  
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)  
Image Size                      : 2560x1598  
Megapixels                      : 4.1
```
## Notas Adicionales
al ver los metadatos de la imagen me di cuenta que el campo de licencia estaba en base64 (`cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9`)
lo pase a cyberchef para decodificarlo y obtuve la flag.
### Referencias
cyberchef from base64
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnQwYUdWZmJUTjBZV1JoZEdGZk1YTmZiVzlrYVdacFpXUjk
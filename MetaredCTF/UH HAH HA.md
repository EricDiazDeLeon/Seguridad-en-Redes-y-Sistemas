## Objetivo 

## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/MetaR$ ls  
r2.7z   'Thermal_camera.png?token=eyJ1c2VyX2lkIjo3MzAsInRlYW1faWQiOjM4NywiZmlsZV9pZCI6MTF9.Zw8hMg.65-H9kREKf5XFW2YjqPJbwoYCik'  
SM.zip   zip_hash.txt  
kali@KaliEND:~/Downloads/PicoCTF/MetaR$ 7z e r2.7z
7-Zip 23.01 (x64) : Copyright (c) 1999-2023 Igor Pavlov : 2023-06-20
 64-bit locale=en_US.UTF-8 Threads:2 OPEN_MAX:1024

Scanning the drive for archives:
1 file, 222 bytes (1 KiB)

Extracting archive: r2.7z

Enter password (will not be echoed):
--
Path = r2.7z
Type = 7z
Physical Size = 222
Headers Size = 190
Method = LZMA2:12 7zAES
Solid = -
Blocks = 1

Everything is Ok

Size:       16
Compressed: 222

FLAG: flagmx{cuv4v3}
```
## Notas Adicionales 
Usé el comando ls para ver qué archivos estaban en esa carpeta. Pude ver varios archivos interesantes, incluyendo uno llamado r2.7z, que es un archivo comprimido en formato .7z despues descomprimí el archivo r2.7z entonces, utilicé 7z para intentar extraer el contenido del archivo r2.7z. El comando me pidió una contraseña, la ingresé y, al parecer, fue la correcta, porque se descomprimió un archivo pequeño de 16 bytes. Todo salió bien, según el mensaje "Everything is Ok".
flag: `flagmx{cuv4v3}`
### Referencias


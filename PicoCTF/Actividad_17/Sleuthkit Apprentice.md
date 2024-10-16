## Objetivo 
Description
Download this disk image and find the flag.
Note: if you are using the webshell, download and extract the disk image into /tmp not your home directory.
Download compressed disk image
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act17$ wget https://artifacts.picoctf.net/c/137/disk.flag.img.gz  
--2024-10-15 22:29:21--  https://artifacts.picoctf.net/c/137/disk.flag.img.gz  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:8600:16:5ec5:2840:93a1, 2600:9000:25ed:9600:16:5ec5:28  
40:93a1, 2600:9000:25ed:b400:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:8600:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 47534568 (45M) [application/octet-stream]  
Grabando a: «disk.flag.img.gz»  
  
disk.flag.img.gz                 100%[========================================================>]  45,33M  5,22MB/s    en 9,6s       
  
2024-10-15 22:29:32 (4,74 MB/s) - «disk.flag.img.gz» guardado [47534568/47534568]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ ls  
disk.flag.img  disk.flag.img.gz  flag.txt  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ rm flag.txt    
kali@KaliEND:~/Downloads/PicoCTF/Act17$ rm disk.flag.img  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ ls  
disk.flag.img.gz  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ gzip -d disk.flag.img.gz  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ fls -o 360448 disk.flag.img -r 3981  
r/r * 2082(realloc):    flag.txt  
r/r 2371:       flag.uni.txt  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ fls -o 360448 disk.flag.img -r 1995  
r/r 2363:       .ash_history  
d/d 3981:       my_folder  
+ r/r * 2082(realloc):  flag.txt  
+ r/r 2371:     flag.uni.txt  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ icat -o 360448 disk.flag.img 2363  
apk add nano  
mkdir my_folder  
cd my_folder/  
nano flag.txt  
ls -al  
iconv -f ascii -t utf16 > flag.uni.txt  
l  
ls -al  
iconv -f ascii -t utf16 flag.txt > flag.uni.txt  
ls -al  
shred  
shred -zu flag.txt    
ls -al  
halt  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ icat -o 360448 disk.flag.img 2371  
picoCTF{by73_5urf3r_adac6cb4}
```
## Notas Adicionales 

Primero, descargué un archivo llamado disk.flag.img.gz desde PicoCTF usando wget. La descarga fue rápida y ya lo tenía en mi carpeta
Luego, descomprimí el archivo disk.flag.img.gz con gzip. Una vez descomprimido, utilicé fls para explorar el contenido de la imagen y encontré un par de archivos interesantes: flag.txt y flag.uni.txt, además de un archivo de historial .ash_history.
Con icat, revisé el historial y vi que había un par de comandos ejecutados. Algunos de ellos eran sobre cómo crear una carpeta, abrir el editor de texto nano, y finalmente convertir el archivo flag.txt a un formato diferente llamado flag.uni.txt.
Finalmente, revisé el contenido del archivo flag.uni.txt, y allí estaba la bandera que estaba buscando: picoCTF{by73_5urf3r_adac6cb4}.
### Referencias


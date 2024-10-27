## Objetivo
```
All we know is the file with the flag is named `down-at-the-bottom.txt`... Disk image: [dds2-alpine.flag.img.gz]
```
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ wget https://mercury.picoctf.net/static/2e54f22211165e9f33a47bdb8a09268b/dds2  
-alpine.flag.img.gz  
--2024-10-26 23:57:11--  https://mercury.picoctf.net/static/2e54f22211165e9f33a47bdb8a09268b/dds2-alpine.flag.img.gz  
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142  
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 29770549 (28M) [application/octet-stream]  
Grabando a: «dds2-alpine.flag.img.gz»  
  
dds2-alpine.flag.img.gz          100%[========================================================>]  28,39M  6,06MB/s    en 5,6s       
  
2024-10-26 23:57:17 (5,07 MB/s) - «dds2-alpine.flag.img.gz» guardado [29770549/29770549]  
  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ ls  
a.out                    Financial_Report_for_ABC_Labs.pdf  shark2.pcapng  suspicious.dd.sda1  
dds2-alpine.flag.img.gz  pico.flag.png                      stegsolve.jar  trace.pcap  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ gunzip dds2-alpine.flag.img.gz    
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ ls  
a.out                 Financial_Report_for_ABC_Labs.pdf  shark2.pcapng  suspicious.dd.sda1  
dds2-alpine.flag.img  pico.flag.png                      stegsolve.jar  trace.pcap  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ mmls dds2-alpine.flag.img    
DOS Partition Table  
Offset Sector: 0  
Units are in 512-byte sectors  
  
     Slot      Start        End          Length       Description  
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)  
001:  -------   0000000000   0000002047   0000002048   Unallocated  
002:  000:000   0000002048   0000262143   0000260096   Linux (0x83)  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ fls -o 2048 dds2-alpine.flag.img  
d/d 26417:      home  
d/d 11: lost+found  
r/r 12: .dockerenv  
d/d 20321:      bin  
d/d 4065:       boot  
d/d 6097:       dev  
d/d 2033:       etc  
d/d 8129:       lib  
d/d 14225:      media  
d/d 16257:      mnt  
d/d 18289:      opt  
d/d 16258:      proc  
d/d 18290:      root  
d/d 16259:      run  
d/d 18292:      sbin  
d/d 12222:      srv  
d/d 16260:      sys  
d/d 18369:      tmp  
d/d 12223:      usr  
d/d 14229:      var  
V/V 32513:      $OrphanFiles  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ fls -o 2048 dds2-alpine.flag.img 18290  
r/r 18291:      down-at-the-bottom.txt  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ fls -o 2048 dds2-alpine.flag.img 18290  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ fls -o 2048 dds2-alpine.flag.img 18290  
                                                    ls  
a.out                 Financial_Report_for_ABC_Labs.pdf  shark2.pcapng  suspicious.dd.sda1  
dds2-alpine.flag.img  pico.flag.png                      stegsolve.jar  trace.pcap  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ icat -o 2048 dds2-alpine.flag.img 18291  
  _     _     _     _     _     _     _     _     _     _     _     _     _     
 / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \    
( p ) ( i ) ( c ) ( o ) ( C ) ( T ) ( F ) ( { ) ( f ) ( 0 ) ( r ) ( 3 ) ( n )  
 \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/    
  _     _     _     _     _     _     _     _     _     _     _     _     _     
 / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \    
( s ) ( 1 ) ( c ) ( 4 ) ( t ) ( 0 ) ( r ) ( _ ) ( n ) ( 0 ) ( v ) ( 1 ) ( c )  
 \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/    
  _     _     _     _     _     _     _     _     _     _     _     
 / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \    
( 3 ) ( _ ) ( d ) ( b ) ( 5 ) ( 9 ) ( d ) ( a ) ( a ) ( 5 ) ( } )  
 \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/    
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$
```
## Notas Adicionales
no me alcanzo el tiempo para subir esta. ;c
flag: `picoCTF{f0r3ns1c4t0r_n0v1c3_db59daa5}`
### Referencias
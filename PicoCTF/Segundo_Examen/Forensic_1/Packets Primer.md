## Objetivo
Download the packet capture file and use packet analysis software to find the flag.

- [Download packet capture](https://artifacts.picoctf.net/c/196/network-dump.flag.pcap)
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_1$ wget https://artifacts.picoctf.net/c/196/network-dump.flag.pcap  
--2024-10-26 23:50:48--  https://artifacts.picoctf.net/c/196/network-dump.flag.pcap  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:c00:16:5ec5:2840:93a1, 2600:9000:25ed:b200:16:5ec5:284  
0:93a1, 2600:9000:25ed:e600:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:c00:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 778 [application/octet-stream]  
Grabando a: «network-dump.flag.pcap»  
  
network-dump.flag.pcap           100%[========================================================>]     778  --.-KB/s    en 0s         
  
2024-10-26 23:50:49 (15,0 MB/s) - «network-dump.flag.pcap» guardado [778/778]  
  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_1$ ls  
dump.pcap  flag.zip                Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png  Texto.txt  
flag       network-dump.flag.pcap  stegsolve.jar
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_1$ python3  
Python 3.12.6 (main, Sep  7 2024, 14:20:15) [GCC 14.2.0] on linux  
Type "help", "copyright", "credits" or "license" for more information.  
>>> "p i c o C T F { p 4 c k 3 7 _ 5 h 4 r k _ 0 1 b 0 a 0 d 6 }".replace(" ","")  
'picoCTF{p4ck37_5h4rk_01b0a0d6}'  
>>> exit()  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_1$

```
## Notas Adicionales
Descargamos la pcap la abri con wireshark y segui el TPC steam del primer elemento, encontre la flag:
`p i c o C T F { p 4 c k 3 7 _ 5 h 4 r k _ 0 1 b 0 a 0 d 6 }`
quite los espacios con python y listo:
`picoCTF{p4ck37_5h4rk_01b0a0d6}`
### Referencias
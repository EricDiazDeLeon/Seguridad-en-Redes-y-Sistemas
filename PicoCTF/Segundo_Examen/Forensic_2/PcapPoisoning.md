## Objetivo
How about some hide and seek heh?Download this [file](https://artifacts.picoctf.net/c/373/trace.pcap) and find the flag.
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ wget https://artifacts.picoctf.net/c/373/trace.pcap  
--2024-10-26 18:16:16--  https://artifacts.picoctf.net/c/373/trace.pcap  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:9a00:16:5ec5:2840:93a1, 2600:9000:25ed:400:16:5ec5:284  
0:93a1, 2600:9000:25ed:ee00:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:9a00:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 106715 (104K) [application/octet-stream]  
Grabando a: «trace.pcap»  
  
trace.pcap                       100%[========================================================>] 104,21K  --.-KB/s    en 0,06s      
  
2024-10-26 18:16:17 (1,81 MB/s) - «trace.pcap» guardado [106715/106715]  
  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/forensic_2$ ls  
trace.pcap
```
## Notas Adicionales
usando wireshark vemos que hay muchisimos tcps entonces buscamos todos los tcp que contengan picoctf, para hacer esto en la barra de busqueda escribi: `tcp contains "picoCTF"`
al encontrarlo y darle click encontramos la flag en un formato:
```bash
0000   45 00 00 52 00 01 00 00 40 06 c3 90 ac 10 00 02   E..R....@.......
0010   0a fd 00 06 00 14 00 15 00 00 00 00 00 00 00 00   ................
0020   50 02 20 00 50 18 00 00 70 69 63 6f 43 54 46 7b   P. .P...picoCTF{
0030   50 36 34 50 5f 34 4e 34 4c 37 53 31 53 5f 53 55   P64P_4N4L7S1S_SU
0040   35 35 33 35 35 46 55 4c 5f 34 64 37 32 64 66 63   55355FUL_4d72dfc
0050   63 7d                                             c}
```
tomamos la flag y resulta ser correcta.
`picoCTF{P64P_4N4L7S1S_SU55355FUL_4d72dfcc}`
### Referencias
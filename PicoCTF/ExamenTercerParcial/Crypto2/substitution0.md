## Objetivo
A message has come in but it seems to be all scrambled. Luckily it seems to have the key at the beginning. Can you crack this substitution cipher?Download the message [here](https://artifacts.picoctf.net/c/153/message.txt).
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/substitution0$ wget https://artifacts.picoctf.net/c/153/message.txt  
--2024-11-22 22:55:55--  https://artifacts.picoctf.net/c/153/message.txt  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:9c00:16:5ec5:2840:93a1, 2600:9000:25ed:2200:16:5ec5:28  
40:93a1, 2600:9000:25ed:9600:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:9c00:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 670 [application/octet-stream]  
Grabando a: «message.txt»  
  
message.txt                      100%[========================================================>]     670  --.-KB/s    en 0s         
  
2024-11-22 22:55:56 (7,05 MB/s) - «message.txt» guardado [670/670]  
  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/substitution0$ ls  
message.txt  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/substitution0$ cat message.txt    
OHNFUMWSVZLXEGCPTAJDYIRKQB    
  
Suauypcg Xuwaogf oacju, rvds o waoiu ogf jdoduxq ova, ogf hacywsd eu dsu huudxu  
mace o wxojj noju vg rsvns vd roj ugnxcjuf. Vd roj o huoydvmyx jnoaohouyj, ogf, od  
dsod dveu, yglgcrg dc godyaoxvjdj—cm ncyaju o wauod pavbu vg o jnvugdvmvn pcvgd  
cm ivur. Dsuau ruau drc acygf hxonl jpcdj guoa cgu ukdauevdq cm dsu honl, ogf o  
xcgw cgu guoa dsu cdsua. Dsu jnoxuj ruau uknuufvgwxq soaf ogf wxcjjq, rvds oxx dsu  
oppuoaognu cm hyagvjsuf wcxf. Dsu ruvwsd cm dsu vgjund roj iuaq aueoalohxu, ogf,  
dolvgw oxx dsvgwj vgdc ncgjvfuaodvcg, V ncyxf soafxq hxoeu Zypvdua mca svj cpvgvcg  
aujpundvgw vd.  
  
Dsu mxow vj: pvncNDM{5YH5717Y710G_3I0XY710G_03055505}
```
## Notas Adicionales
Deciframos el mensaje usando [Boxentriq](https://www.boxentriq.com/code-breaking/keyed-caesar-cipher) 
`picoCTF{5UB5717U710N_3V0LU710N_03055505}`
`
### Referencias
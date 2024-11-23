## Objetivo
It seems that another encrypted message has been intercepted. The encryptor seems to have learned their lesson though and now there isn't any punctuation! Can you still crack the cipher?Download the message [here](https://artifacts.picoctf.net/c/113/message.txt).
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/substitution2$ wget https://artifacts.picoctf.net/c/113/message.txt  
--2024-11-22 23:01:07--  https://artifacts.picoctf.net/c/113/message.txt  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:9c00:16:5ec5:2840:93a1, 2600:9000:25ed:8400:16:5ec5:28  
40:93a1, 2600:9000:25ed:600:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:9c00:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 1288 (1,3K) [application/octet-stream]  
Grabando a: «message.txt»  
  
message.txt                      100%[========================================================>]   1,26K  --.-KB/s    en 0s         
  
2024-11-22 23:01:08 (17,2 MB/s) - «message.txt» guardado [1288/1288]  
  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/substitution2$ ls  
message.txt  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/substitution2$ cat message.txt    
isnfnnpctitnznfmxhisnfwnxxntimjxctsnascdstushhxuhgqbinftnubfciruhgqnicichktckuxbackdurjnfqmifchimkabturjnfusmxxnkdnisntnuhgqnicich  
ktehubtqfcgmfcxrhktrtingtmagckctifmichkebkamgnkimxtwscusmfnznfrbtnebxmkagmfonimjxntocxxtshwnznfwnjnxcnznisnqfhqnfqbfqhtnhemscdstus  
hhxuhgqbinftnubfciruhgqnicichkctkhihkxrihinmuszmxbmjxntocxxtjbimxthihdnitibankitckinfntinackmkanpucinamjhbiuhgqbinftucnkunanenktcz  
nuhgqnicichktmfnheinkxmjhfchbtmeemcftmkauhgnahwkihfbkkckdusnuoxctitmkanpnubickduhkecdtufcqitheenktnhkisnhisnfsmkactsnmzcxrehubtnah  
knpqxhfmichkmkacgqfhzctmichkmkaheinksmtnxngnkitheqxmrwnjnxcnznmuhgqnicichkihbusckdhkisnheenktcznnxngnkitheuhgqbinftnubfcirctisnfne  
hfnmjniinfznscuxnehfinusnzmkdnxctgihtibankitckmgnfcumkscdstushhxtebfisnfwnjnxcnznismimkbkanftimkackdheheenktczninuskcvbntctnttnkic  
mxehfghbkickdmkneenuicznanenktnmkaismiisnihhxtmkauhkecdbfmichkehubtnkuhbkinfnackanenktcznuhgqnicichktahntkhixnmatibankitihokhwisnc  
fnkngrmtneenuicznxrmtinmusckdisngihmuicznxrisckoxconmkmiimuonfqcuhuiectmkheenktcznxrhfcnkinascdstushhxuhgqbinftnubfciruhgqnicichki  
smitnnotihdnknfminckinfntickuhgqbinftucnkunmghkdscdstushhxnftinmusckdisngnkhbdsmjhbiuhgqbinftnubfcirihqcvbnisncfubfchtcirghiczmick  
disngihnpqxhfnhkisncfhwkmkankmjxckdisngihjniinfanenkaisncfgmusckntisnexmdctqcuhUIE{K6F4G_4K41R515_15_73A10B5_702E03EU}kali@KaliEND  
:~/Downloads/PicoCTF/Exam3erParcial/substitution2$
```
## Notas Adicionales
decodifique usando https://www.guballa.de/substitution-solver
`picoCTF{N6R4M_4N41Y515_15_73D10U5_702F03FC}`
### Referencias
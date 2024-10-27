## Objetivo
Download this packet capture and find the flag.

- [Download packet capture](https://artifacts.picoctf.net/c/134/capture.flag.pcap)
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Examen2$ wget https://artifacts.picoctf.net/c/134/capture.flag.pcap  
--2024-10-26 17:08:01--  https://artifacts.picoctf.net/c/134/capture.flag.pcap  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:3e00:16:5ec5:2840:93a1, 2600:9000:25ed:9c00:16:5ec5:28  
40:93a1, 2600:9000:25ed:400:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:3e00:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 7518 (7,3K) [application/octet-stream]  
Grabando a: «capture.flag.pcap»  
  
capture.flag.pcap                100%[========================================================>]   7,34K  --.-KB/s    en 0s         
  
2024-10-26 17:08:02 (94,1 MB/s) - «capture.flag.pcap» guardado [7518/7518]  
  
kali@KaliEND:~/Downloads/PicoCTF/Examen2$ ls  
capture.flag.pcap  cat.jpg  
kali@KaliEND:~/Downloads/PicoCTF/Examen2$ openssl des3 -d -salt -in file.des3 -out file.txt -k supersecretpassword123  
*** WARNING : deprecated key derivation used.  
Using -iter or -pbkdf2 would be better.  
kali@KaliEND:~/Downloads/PicoCTF/Examen2$ ls  
capture.flag.pcap  cat.jpg  file.des3  file.txt  
kali@KaliEND:~/Downloads/PicoCTF/Examen2$ cat file.txt    
picoCTF{nc_73115_411_dd54ab67}
```
## Notas Adicionales
usando wireshark encontramos una conversacion en la cual se menciona un comando de desencripcion ademas de un numero `9002`
conversacion:
```
Hey, how do you decrypt this file again?

  

You're serious?

  

Yeah, I'm serious

  

*sigh* openssl des3 -d -salt -in file.des3 -out file.txt -k supersecretpassword123

  

Ok, great, thanks.

  

Let's use Discord next time, it's more secure.

  

C'mon, no one knows we use this program like this!

  

Whatever.

  

Hey.

  

Yeah?

  

Could you transfer the file to me again?

  

Oh great. Ok, over 9002?

  

Yeah, listening.

  

Sent it

  

Got it.

  

You're unbelievable
```
segui buscando hasta que encontre un string que decia salted al principio:
```bash
Salted__..

.%..[eC.lR...H{.R.m....P..R/..2....d@
```
lo guarde como raw y le puse el mismo nombre que tenia en el comando de la conversación anterior: `file.des3`
y por ultimo utilizamos dicho comando y obtenemos la flag en un .txt al que le hacemos cat.
flag: `picoCTF{nc_73115_411_dd54ab67}`
### Referencias
wireshark

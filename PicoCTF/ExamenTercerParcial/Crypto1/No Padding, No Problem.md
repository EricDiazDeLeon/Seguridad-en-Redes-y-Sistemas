## Objetivo
Oracles can be your best friend, they will decrypt anything, except the flag's ciphertext. How will you break it? Connect with `nc mercury.picoctf.net 30048`.
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/Nopadding$ nc mercury.picoctf.net 30048  
Welcome to the Padding Oracle Challenge  
This oracle will take anything you give it and decrypt using RSA. It will not accept the ciphertext with the secret message... Goo  
d Luck!  
  
  
n: 1299830691578680591548163073944368026391985912771996042616443054722425809577759822305879694430304793069614441783355697736799448  
6515399620682136547702585384223271694371012260193816378495241068982920724715230034250811104965196283396301851810698709678608929429  
1435317545378181045087473136651483131797297210052417  
e: 65537  
ciphertext: 7269049035454872078207592964527159291726986818177139759113323416644857583115277779692763472105509384758340870020436428  
2577925714242082891487250460555215633684511806964225945888086828664799442128180660423001521000536766844001956760365152046068247135  
393635838350853823106863488498032206519276709723359474651893  
  
  
Give me ciphertext to decrypt: ^C  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/Nopadding$ nano solve.py  
(Entorno) kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/Nopadding$ python3 solve.py    
[+] Opening connection to mercury.picoctf.net on port 30048: Done  
/home/kali/Downloads/PicoCTF/Exam3erParcial/Nopadding/solve.py:17: BytesWarning: Text is not bytes; assuming ASCII, no guarantees.  
See https://docs.pwntools.com/#bytes  
 r.sendlineafter(b'Give me ciphertext to decrypt: ', str(payload))  
Doubled Plain: 5805500603917000789469132367349117701399314977025561535134874408934066290348027185346455380749385028907694257953798  
46471930  
Plain Text Hex: 7069636f4354467b6d347962335f54683073655f6d337335346733735f3472335f646966757272656e745f353035323632307d  
Plain Text: picoCTF{m4yb3_Th0se_m3s54g3s_4r3_difurrent_5052620}  
[*] Closed connection to mercury.picoctf.net port 30048  
(Entorno) kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/Nopadding$
```
solve.py:
```bash
from pwn import *  
import binascii  
  
r = remote('mercury.picoctf.net', 30048)  
r.recvlines(4)  
  
r.recvuntil(b'n: ')  
n = int(r.recvline().strip())  
  
r.recvuntil(b'e: ')  
e = int(r.recvline().strip())  
  
r.recvuntil(b'ciphertext: ')  
c = int(r.recvline().strip())  
  
payload = c * pow(2,e,n)  
r.sendlineafter(b'Give me ciphertext to decrypt: ', str(payload))  
  
r.recvuntil(b'Here you go: ')  
doubled_plain = int(r.recvline().strip())  
print("Doubled Plain:", doubled_plain)  
  
plain_hex = hex(doubled_plain // 2)[2:]  
plain_bytes = bytes.fromhex(plain_hex)  
print("Plain Text Hex:", plain_hex)  
print("Plain Text:", plain_bytes.decode())  
  
r.close()
```
## Notas Adicionales
creamos el archivo solve.py para automatizar el netcat y obtener la bandera.
flag: `picoCTF{m4yb3_Th0se_m3s54g3s_4r3_difurrent_5052620}`
### Referencias
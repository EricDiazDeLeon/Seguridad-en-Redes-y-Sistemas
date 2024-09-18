## Objetivo 
Using a Secure Shell (SSH) is going to be pretty important.Can you `ssh` as `ctf-player` to `titan.picoctf.net` at port `56141` to get the flag?You'll also need the password `83dcefb7`. If asked, accept the fingerprint with `yes`.If your device doesn't have a shell, you can use: [https://webshell.picoctf.org](https://webshell.picoctf.org/)If you're not sure what a shell is, check out our Primer: [https://primer.picoctf.com/#_the_shell](https://primer.picoctf.com/#_the_shell)
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/parte1$ ssh ctf-player@titan.picoctf.net -p 56141  
The authenticity of host '[titan.picoctf.net]:56141 ([3.139.174.234]:56141)' can't be established.  
ED25519 key fingerprint is SHA256:4S9EbTSSRZm32I+cdM5TyzthpQryv5kudRP9PIKT7XQ.  
This key is not known by any other names.  
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes  
Warning: Permanently added '[titan.picoctf.net]:56141' (ED25519) to the list of known hosts.  
ctf-player@titan.picoctf.net's password:    
Welcome ctf-player, here's your flag: picoCTF{s3cur3_c0nn3ct10n_8969f7d3}  
Connection to titan.picoctf.net closed.  
kali@KaliEND:~/Downloads/PicoCTF/parte1$
```
## Notas Adicionales 
solo fue conectarse a un servidor mediante ssh
la verdad demasiado facil pero quien se fija.
### Referencias

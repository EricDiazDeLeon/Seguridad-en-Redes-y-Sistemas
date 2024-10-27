## Objetivo
I sent out 2 invitations to all of my friends for my birthday! I'll know if they get stolen because the two invites look similar, and they even have the same md5 hash, but they are slightly different! You wouldn't believe how long it took me to find a collision. Anyway, see if you're invited by submitting 2 PDFs to my website. [http://mercury.picoctf.net:55343/](http://mercury.picoctf.net:55343/)
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Examen2/web_2$ wget https://www.mscs.dal.ca/~selinger/md5collision/hello  
--2024-10-26 21:24:07--  https://www.mscs.dal.ca/~selinger/md5collision/hello  
Resolviendo www.mscs.dal.ca (www.mscs.dal.ca)... 129.173.118.86  
Conectando con www.mscs.dal.ca (www.mscs.dal.ca)[129.173.118.86]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 4072 (4,0K)  
Grabando a: «hello»  
  
hello                            100%[========================================================>]   3,98K  --.-KB/s    en 0s         
  
2024-10-26 21:24:08 (47,2 MB/s) - «hello» guardado [4072/4072]  
  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/web_2$ wget https://www.mscs.dal.ca/~selinger/md5collision/erase  
--2024-10-26 21:24:15--  https://www.mscs.dal.ca/~selinger/md5collision/erase  
Resolviendo www.mscs.dal.ca (www.mscs.dal.ca)... 129.173.118.86  
Conectando con www.mscs.dal.ca (www.mscs.dal.ca)[129.173.118.86]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 4072 (4,0K)  
Grabando a: «erase»  
  
erase                            100%[========================================================>]   3,98K  --.-KB/s    en 0,007s     
  
2024-10-26 21:24:16 (579 KB/s) - «erase» guardado [4072/4072]  
  
kali@KaliEND:~/Downloads/PicoCTF/Examen2/web_2$
```
despues de la insersion de los dos archivos con el mismo md5:
```bash
<?php  
  
if (isset($_POST["submit"])) {    $type1 = $_FILES["file1"]["type"];    $type2 = $_FILES["file2"]["type"];    $size1 = $_FILES["file1"]["size"];    $size2 = $_FILES["file2"]["size"];    $SIZE_LIMIT = 18 * 1024;  
  
    if (($size1 < $SIZE_LIMIT) && ($size2 < $SIZE_LIMIT)) {  
        if (($type1 == "application/pdf") && ($type2 == "application/pdf")) {            $contents1 = file_get_contents($_FILES["file1"]["tmp_name"]);            $contents2 = file_get_contents($_FILES["file2"]["tmp_name"]);  
  
            if ($contents1 != $contents2) {  
                if (md5_file($_FILES["file1"]["tmp_name"]) == md5_file($_FILES["file2"]["tmp_name"])) {                    highlight_file("index.php");  
                    die();  
                } else {  
                    echo "MD5 hashes do not match!";  
                    die();  
                }  
            } else {  
                echo "Files are not different!";  
                die();  
            }  
        } else {  
            echo "Not a PDF!";  
            die();  
        }  
    } else {  
        echo "File too large!";  
        die();  
    }  
}  
  
// FLAG: picoCTF{c0ngr4ts_u_r_1nv1t3d_aad886b9}  
  
?>  
<!DOCTYPE html>  
<html lang="en">  
  
<head>  
    <title>It is my Birthday</title>  
  
  
    <link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css" rel="stylesheet">  
  
    <link href="https://getbootstrap.com/docs/3.3/examples/jumbotron-narrow/jumbotron-narrow.css" rel="stylesheet">  
  
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>  
  
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>  
  
  
</head>  
  
<body>  
  
    <div class="container">  
        <div class="header">  
            <h3 class="text-muted">It is my Birthday</h3>  
        </div>  
        <div class="jumbotron">  
            <p class="lead"></p>  
            <div class="row">  
                <div class="col-xs-12 col-sm-12 col-md-12">  
                    <h3>See if you are invited to my party!</h3>  
                </div>  
            </div>  
            <br/>  
            <div class="upload-form">  
                <form role="form" action="/index.php" method="post" enctype="multipart/form-data">  
                <div class="row">  
                    <div class="form-group">  
                        <input type="file" name="file1" id="file1" class="form-control input-lg">  
                        <input type="file" name="file2" id="file2" class="form-control input-lg">  
                    </div>  
                </div>  
                <div class="row">  
                    <div class="col-xs-12 col-sm-12 col-md-12">  
                        <input type="submit" class="btn btn-lg btn-success btn-block" name="submit" value="Upload">  
                    </div>  
                </div>  
                </form>  
            </div>  
        </div>  
    </div>  
    <footer class="footer">  
        <p>&copy; PicoCTF</p>  
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
```
## Notas Adicionales
el sitio nos requiere 2 archivos pdf, a lo cual se supone que este reto se trata de hacer colision de archivos con la misma firma md5, por lo que busque 2 archivos con el mismo md5 en este sitio https://www.mscs.dal.ca/~selinger/md5collision/
cuando los inserte me mando error diciendo que no eran pdf, asi que les cambie la extension a .pdf al fin y alcabo no cambia la firma md5
y obtuve la flag.
flag: `picoCTF{c0ngr4ts_u_r_1nv1t3d_aad886b9}`
### Referencias
https://www.mscs.dal.ca/~selinger/md5collision/
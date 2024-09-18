## Objetivo 
Unzip this archive and find the file named 'uber-secret.txt'

- [Download zip file](https://artifacts.picoctf.net/c/501/files.zip)
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ wget https://artifacts.picoctf.net/c/501/files.zip  
--2024-09-17 22:47:01--  https://artifacts.picoctf.net/c/501/files.zip  
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:da00:16:5ec5:2840:93a1, 2600:9000:25  
ed:4e00:16:5ec5:2840:93a1, 2600:9000:25ed:a000:16:5ec5:2840:93a1, ...  
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:25ed:da00:16:5ec5:2840:93a1|:443... conn  
ected.  
HTTP request sent, awaiting response... 200 OK  
Length: 3995553 (3.8M) [application/octet-stream]  
Saving to: ‘files.zip’  
  
files.zip                   100%[=========================================>]   3.81M  4.48MB/s    in 0.9s       
  
2024-09-17 22:47:02 (4.48 MB/s) - ‘files.zip’ saved [3995553/3995553]  
  
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ ls  
files.zip  message.txt  
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ unzip files.zip    
Archive:  files.zip  
  creating: files/  
  creating: files/satisfactory_books/  
  creating: files/satisfactory_books/more_books/  
 inflating: files/satisfactory_books/more_books/37121.txt.utf-8     
 inflating: files/satisfactory_books/23765.txt.utf-8     
 inflating: files/satisfactory_books/16021.txt.utf-8     
 inflating: files/13771.txt.utf-8      
  creating: files/adequate_books/  
  creating: files/adequate_books/more_books/  
  creating: files/adequate_books/more_books/.secret/  
  creating: files/adequate_books/more_books/.secret/deeper_secrets/  
  creating: files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/  
extracting: files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt     
 inflating: files/adequate_books/more_books/1023.txt.utf-8     
 inflating: files/adequate_books/46804-0.txt     
 inflating: files/adequate_books/44578.txt.utf-8     
  creating: files/acceptable_books/  
  creating: files/acceptable_books/more_books/  
 inflating: files/acceptable_books/more_books/40723.txt.utf-8     
 inflating: files/acceptable_books/17880.txt.utf-8     
 inflating: files/acceptable_books/17879.txt.utf-8     
 inflating: files/14789.txt.utf-8      
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ ls  
files  files.zip  message.txt
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in$ cd files
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in/files$ ls  
13771.txt.utf-8  14789.txt.utf-8  acceptable_books  adequate_books  satisfactory_books
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in/files$ find -name uber-secret.txt  
./adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt  
kali@KaliEND:~/Downloads/PicoCTF/parte1/drop-in/files$ cat ./adequate_books/more_books/.secret/deeper_secrets/  
deepest_secrets/uber-secret.txt  
picoCTF{f1nd_15_f457_ab443fd1}
```
## Notas Adicionales 
Dentro del zip habian muchos archivos y carpetas, use find para buscar la flag y una vez la encontre le hice cat directamente a la direccion para obtener la Flag.
### Referencias


## Objetivo
What can you do with this file?I forgot the key to my safe but this [file](https://artifacts.picoctf.net/c/287/SafeOpener.class) is supposed to help me with retrieving the lost key. Can you help me unlock my safe?
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act22$ wget https://artifacts.picoctf.net/c/287/SafeOpener.class  
--2024-10-30 10:21:36--  https://artifacts.picoctf.net/c/287/SafeOpener.class  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.26, 3.161.55.61, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[3.161.55.100]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 2036 (2,0K) [application/octet-stream]  
Grabando a: «SafeOpener.class»  
  
SafeOpener.class                 100%[========================================================>]   1,99K  --.-KB/s    en 0s         
  
2024-10-30 10:21:46 (22,2 MB/s) - «SafeOpener.class» guardado [2036/2036]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act22$ ls  
SafeOpener.class
kali@KaliEND:~/Downloads/PicoCTF/Act22$ strings SafeOpener.class    
<init>  
Code  
LineNumberTable  
LocalVariableTable  
this  
LSafeOpener;  
main  
([Ljava/lang/String;)V  
isOpen  
args  
[Ljava/lang/String;  
keyboard  
Ljava/io/BufferedReader;  
encoder  
Encoder  
InnerClasses  
Ljava/util/Base64$Encoder;  
encodedkey  
Ljava/lang/String;  
StackMapTable  
Exceptions  
openSafe  
(Ljava/lang/String;)Z  
password  
SourceFile  
SafeOpener.java  
java/io/BufferedReader  
java/io/InputStreamReader  
Enter password for the safe:    
java/lang/StringBuilder  
You have     
attempt(s) left  
,picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_b427942b}  
Sesame open  
Password is incorrect  
SafeOpener  
java/lang/Object  
java/util/Base64$Encoder  
java/lang/String  
java/io/IOException  
java/lang/System  
Ljava/io/InputStream;  
(Ljava/io/InputStream;)V  
(Ljava/io/Reader;)V  
java/util/Base64  
getEncoder  
()Ljava/util/Base64$Encoder;  
Ljava/io/PrintStream;  
java/io/PrintStream  
print  
(Ljava/lang/String;)V  
readLine  
()Ljava/lang/String;  
getBytes  
()[B  
encodeToString  
([B)Ljava/lang/String;  
println  
append  
-(Ljava/lang/String;)Ljava/lang/StringBuilder;  
(I)Ljava/lang/StringBuilder;  
toString  
equals  
(Ljava/lang/Object;)Z
kali@KaliEND:~/Downloads/PicoCTF/Act22$ jd-gui
```
## Notas Adicionales
jd-gui es una herramienta para abrir archivos .class y decompilarlos
`picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_b427942b}`
### Referencias
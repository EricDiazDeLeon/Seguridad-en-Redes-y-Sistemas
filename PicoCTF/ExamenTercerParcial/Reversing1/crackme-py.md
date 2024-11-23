## Objetivo
[crackme.py](https://mercury.picoctf.net/static/fd0e358d4b82695c220c0d6013c11484/crackme.py)
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/crackme$ wget https://mercury.picoctf.net/static/fd0e358d4b82695c220c0d6013c11484/  
crackme.py  
--2024-11-22 23:41:34--  https://mercury.picoctf.net/static/fd0e358d4b82695c220c0d6013c11484/crackme.py  
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142  
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 1463 (1,4K) [application/octet-stream]  
Grabando a: «crackme.py»  
  
crackme.py                       100%[========================================================>]   1,43K  --.-KB/s    en 0s         
  
2024-11-22 23:41:34 (28,5 MB/s) - «crackme.py» guardado [1463/1463]  
  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/crackme$ ls  
crackme.py  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/crackme$ cat crackme.py    
# Hiding this really important number in an obscure piece of code is brilliant!  
# AND it's encrypted!  
# We want our biggest client to know his information is safe with us.  
bezos_cc_secret = "A:4@r%uL`M-^M0c0AbcM-MFE055a4ce`eN"  
  
# Reference alphabet  
alphabet = "!\"#$%&'()*+,-./0123456789:;<=>?@ABCDEFGHIJKLMNOPQRSTUVWXYZ"+ \  
           "[\\]^_`abcdefghijklmnopqrstuvwxyz{|}~"  
  
  
  
def decode_secret(secret):  
   """ROT47 decode  
  
   NOTE: encode and decode are the same operation in the ROT cipher family.  
   """  
  
   # Encryption key  
   rotate_const = 47  
  
   # Storage for decoded secret  
   decoded = ""  
  
   # decode loop  
   for c in secret:  
       index = alphabet.find(c)  
       original_index = (index + rotate_const) % len(alphabet)  
       decoded = decoded + alphabet[original_index]  
  
   print(decoded)  
  
  
  
def choose_greatest():  
   """Echo the largest of the two numbers given by the user to the program  
  
   Warning: this function was written quickly and needs proper error handling  
   """  
  
   user_value_1 = input("What's your first number? ")  
   user_value_2 = input("What's your second number? ")  
   greatest_value = user_value_1 # need a value to return if 1 & 2 are equal  
  
   if user_value_1 > user_value_2:  
       greatest_value = user_value_1  
   elif user_value_1 < user_value_2:  
       greatest_value = user_value_2  
  
   print( "The number with largest positive magnitude is "  
       + str(greatest_value) )  
  
  
  
choose_greatest()
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/crackme$ nano solve.py  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/crackme$ nano solve.py  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/crackme$ python3 solve.py    
picoCTF{1|\/|_4_p34|\|ut_dd2c4616}
```

solve.py:
```bash
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/crackme$ cat solve.py    
# Hiding this really important number in an obscure piece of code is brilliant!  
# AND it's encrypted!  
# We want our biggest client to know his information is safe with us.  
bezos_cc_secret = "A:4@r%uL`M-^M0c0AbcM-MFE055a4ce`eN"  
# Reference alphabet  
alphabet = "!\"#$%&'()*+,-./0123456789:;<=>?@ABCDEFGHIJKLMNOPQRSTUVWXYZ"+ \  
           "[\\]^_`abcdefghijklmnopqrstuvwxyz{|}~"  
def decode_secret(secret):  
   """ROT47 decode  
      
   NOTE: encode and decode are the same operation in the ROT cipher family.  
   """  
   # Encryption key  
   rotate_const = 47  
   # Storage for decoded secret  
   decoded = ""  
   # decode loop  
   for c in secret:  
       index = alphabet.find(c)  
       original_index = (index + rotate_const) % len(alphabet)  
       decoded = decoded + alphabet[original_index]  
   print(decoded)  
def choose_greatest():  
   """Echo the largest of the two numbers given by the user to the program  
      
   Warning: this function was written quickly and needs proper error handling  
   """  
   user_value_1 = input("What's your first number? ")  
   user_value_2 = input("What's your second number? ")  
   greatest_value = user_value_1 # need a value to return if 1 & 2 are equal  
   if user_value_1 > user_value_2:  
       greatest_value = user_value_1  
   elif user_value_1 < user_value_2:  
       greatest_value = user_value_2  
   print( "The number with largest positive magnitude is "  
       + str(greatest_value) )  
#choose_greatest()  
decode_secret(bezos_cc_secret)
```
## Notas Adicionales
Modificamos el código para decodificar la contraseña.
`picoCTF{1|\/|_4_p34|\|ut_dd2c4616}`
### Referencias
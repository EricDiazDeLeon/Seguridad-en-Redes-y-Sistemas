## Objetivo 
How well can you perfom basic binary operations?
## Solución  
```bash
ericdiaz-picoctf@webshell:~$ nc titan.picoctf.net 64053

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 11100110
Binary Number 2: 10011111


Question 1/6:
Operation 1: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 10000110
Correct!

Question 2/6:
Operation 2: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 110000101
Correct!

Question 3/6:
Operation 3: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 11100110000
Incorrect. Try again
Enter the binary result: 111001100
Correct!

Question 4/6:
Operation 4: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 11111111
Correct!

Question 5/6:
Operation 5: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 01001111
Correct!

Question 6/6:
Operation 6: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 1000111010101010
Incorrect. Try again
Enter the binary result: 1000111011011010
Correct!

Enter the results of the last operation in hexadecimal: 8EDA

Correct answer!
The flag is: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_d9a7ddd2}
```
## Notas Adicionales 

### Referencias

## Descripción 
```bash
Decodificar la bandera que se muestra en el archivo python: 
|from hidden import flag, shift|
||||
|||def encode(data, shift):|
|||enc = ''|
|||for _ in data:|
|||enc += chr((ord(_)+shift) % 0xff)|
|||return enc|
||||
|||assert encode(flag, shift) == '-3(.4?B,5*9@7;065&0:&:6&-(5*@D'|
```
[](https://github.com/armandoportillo0101/Seguridad-de-Redes/blob/main/Plantilla.md#objetivo)
## Solución
```
|def decode(encoded_data, shift):|
|||dec = ''|
|||for char in encoded_data:|
|||dec += chr((ord(char) - shift) % 0xff)|
|||return dec
||||
||||
|||encoded_flag = '-3(.4?B,5*9@7;065&0:&:6&-(5*@D'|
||||
||||
|||for shift in range(1, 256):|
|||decoded_flag = decode(encoded_flag, shift)|
|||print(f"Shift {shift}: {decoded_flag}")|

flag: flagmx{encryption_is_so_fancy}
```
[](https://github.com/armandoportillo0101/Seguridad-de-Redes/blob/main/Plantilla.md#soluci%C3%B3n)

## Notas Adicionales
-Se tiene que meter el codigo de la solución en ciclo hasta sacar la bandera y ejecutarlo hasta que nos de algo con sentido.
[](https://github.com/armandoportillo0101/Seguridad-de-Redes/blob/main/Plantilla.md#notas-adicionales)

### Referencias
## Objetivo
Connect to this PostgreSQL server and find the flag!`psql -h saturn.picoctf.net -p 50245 -U postgres pico`Password is `postgres`
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Examen2/web_1$ psql -h saturn.picoctf.net -p 50245 -U postgres pico  
Contraseña para usuario postgres:    
psql (17.0 (Debian 17.0-1+b2), servidor 15.2 (Debian 15.2-1.pgdg110+1))  
Digite «help» para obtener ayuda.  
  
pico=# help  
Está usando psql, la interfaz de línea de órdenes de PostgreSQL.  
Digite:  \copyright para ver los términos de distribución  
      \h para ayuda de órdenes SQL  
      \? para ayuda de órdenes psql  
      \g o punto y coma («;») para ejecutar la consulta  
      \q para salir  
pico=# \d  
       Listado de relaciones  
Esquema | Nombre | Tipo  |  Dueño      
---------+--------+-------+----------  
public  | flags  | tabla | postgres  
(1 fila)  
  
pico=# select * from flags  
pico-# select * from flags;  
ERROR:  syntax error at or near "select"  
LÍNEA 2: select * from flags;  
        ^  
pico=# SELECT * FROM flags;  
id | firstname | lastname  |                address                    
----+-----------+-----------+----------------------------------------  
 1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_31fd14c0}  
 2 | Leia      | Organa    | Alderaan  
 3 | Han       | Solo      | Corellia  
(3 filas)  
  
pico=#
```
## Notas Adicionales
accedí al servidor usando `psql -h saturn.picoctf.net -p 50245 -U postgres pico`y la contraseña  `postgres` , una ves dentro use el comando \d para ver todas las tablas, y me equivoque un par de veces con la sintaxis de sql jaja, luego de rectificar seleccione todo de la tabla flags y ahi estaba la flag:
`picoCTF{L3arN_S0m3_5qL_t0d4Y_31fd14c0}`
### Referencias
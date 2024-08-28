## Objetivo 
The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

- human-readable
- 1033 bytes in size
- not executable
## Datos de acceso al nivel 
bandit5
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

## Solución  
```
bandit5@bandit:~$ ls
inhere
bandit5@bandit:~$ ls -la
total 24
drwxr-xr-x  3 root root    4096 Jul 17 15:57 .
drwxr-xr-x 70 root root    4096 Jul 17 15:58 ..
-rw-r--r--  1 root root     220 Mar 31 08:41 .bash_logout
-rw-r--r--  1 root root    3771 Mar 31 08:41 .bashrc
drwxr-x--- 22 root bandit5 4096 Jul 17 15:57 inhere
-rw-r--r--  1 root root     807 Mar 31 08:41 .profile
bandit5@bandit:~$ cd inhere/maybehere
maybehere00/ maybehere03/ maybehere06/ maybehere09/ maybehere12/ maybehere15/ maybehere18/
maybehere01/ maybehere04/ maybehere07/ maybehere10/ maybehere13/ maybehere16/ maybehere19/
maybehere02/ maybehere05/ maybehere08/ maybehere11/ maybehere14/ maybehere17/
bandit5@bandit:~$ cd inhere/maybehere
maybehere00/ maybehere03/ maybehere06/ maybehere09/ maybehere12/ maybehere15/ maybehere18/
maybehere01/ maybehere04/ maybehere07/ maybehere10/ maybehere13/ maybehere16/ maybehere19/
maybehere02/ maybehere05/ maybehere08/ maybehere11/ maybehere14/ maybehere17/
bandit5@bandit:~$ cd inhere
bandit5@bandit:~/inhere$ ls
maybehere00  maybehere03  maybehere06  maybehere09  maybehere12  maybehere15  maybehere18
maybehere01  maybehere04  maybehere07  maybehere10  maybehere13  maybehere16  maybehere19
maybehere02  maybehere05  maybehere08  maybehere11  maybehere14  maybehere17
bandit5@bandit:~/inhere$ ls -r
maybehere19  maybehere16  maybehere13  maybehere10  maybehere07  maybehere04  maybehere01
maybehere18  maybehere15  maybehere12  maybehere09  maybehere06  maybehere03  maybehere00
maybehere17  maybehere14  maybehere11  maybehere08  maybehere05  maybehere02
bandit5@bandit:~/inhere$ ls -R
.:
maybehere00  maybehere03  maybehere06  maybehere09  maybehere12  maybehere15  maybehere18
maybehere01  maybehere04  maybehere07  maybehere10  maybehere13  maybehere16  maybehere19
maybehere02  maybehere05  maybehere08  maybehere11  maybehere14  maybehere17

./maybehere00:
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3

./maybehere01:
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3

./maybehere02:
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3

./maybehere03:
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3

./maybehere04:
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3

./maybehere05:
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3

./maybehere06:
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3

./maybehere07:
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3

./maybehere08:
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3

./maybehere09:
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3

./maybehere10:
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3

./maybehere11:
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3

./maybehere12:
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3

./maybehere13:
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3

./maybehere14:
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3

./maybehere15:
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3

./maybehere16:
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3

./maybehere17:
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3

./maybehere18:
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3

./maybehere19:
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3
bandit5@bandit:~/inhere$ find -
-amin                   -fprint0                -mmin                   -quit
-anewer                 -fprintf                -mount                  -readable
-atime                  -fstype                 -mtime                  -regex
-cmin                   -gid                    -name                   -regextype
-cnewer                 -group                  -newer                  -samefile
-context                -help                   -nogroup                -size
-ctime                  -ignore_readdir_race    -noignore_readdir_race  -true
-daystart               -ilname                 -noleaf                 -type
-delete                 -iname                  -nouser                 -uid
-depth                  -inum                   -nowarn                 -used
-empty                  -ipath                  -ok                     -user
-exec                   -iregex                 -okdir                  -version
-execdir                -iwholename             -path                   -warn
-executable             -links                  -perm                   -wholename
-false                  -lname                  -print                  -writable
-fls                    -ls                     -print0                 -xdev
-follow                 -maxdepth               -printf                 -xtype
-fprint                 -mindepth               -prune
bandit5@bandit:~/inhere$ find -type -size 1033c
find: Unknown argument to -type: -
bandit5@bandit:~/inhere$ find -type f -size 1033c
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG








                                                bandit5@bandit:~/inhere$
```

## Notas Adicionales 
ls -R  - lista archivos de forma recursiva, es decir, las carpetas con subcarpetas
find . -type f -size 1033c 
	. significa que busca aqui hacia abajo
	-type especifica que busque un archivo del tipo regular
	size 1044c especifica el tamaño de archivo de 1033c
### Referencias


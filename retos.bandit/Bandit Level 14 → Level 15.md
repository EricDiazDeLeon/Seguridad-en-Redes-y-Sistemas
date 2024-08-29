## Objetivo 
The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.
## Datos de acceso al nivel 
bandit14
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
## Solución  
```
bandit14@bandit:~$ ls
bandit14@bandit:~$ ls -la
total 24
drwxr-xr-x  3 root root 4096 Jul 17 15:57 .
drwxr-xr-x 70 root root 4096 Jul 17 15:58 ..
-rw-r--r--  1 root root  220 Mar 31 08:41 .bash_logout
-rw-r--r--  1 root root 3771 Mar 31 08:41 .bashrc
-rw-r--r--  1 root root  807 Mar 31 08:41 .profile
drwxr-xr-x  2 root root 4096 Jul 17 15:57 .ssh
bandit14@bandit:~$ nc --help
nc: invalid option -- '-'
usage: nc [-46CDdFhklNnrStUuvZz] [-I length] [-i interval] [-M ttl]
          [-m minttl] [-O length] [-P proxy_username] [-p source_port]
          [-q seconds] [-s sourceaddr] [-T keyword] [-V rtable] [-W recvlimit]
          [-w timeout] [-X proxy_protocol] [-x proxy_address[:port]]
          [destination] [port]
bandit14@bandit:~$ nc localhost 30000
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
Correct!
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo


bandit14@bandit:~$

```

## Notas Adicionales 
nc (Netcat) es una herramienta que permite conectarse a un host remoto, tambien podemos abrir un puerto.

### Referencias


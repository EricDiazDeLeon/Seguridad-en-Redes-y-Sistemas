## Objetivo 
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.
## Datos de acceso al nivel 
bandit21
EeoULMCra2q0dSkYj561DX7s1CpBuOBt
## Solución  
```bash
bandit21@bandit:~$ ls
bandit21@bandit:~$ ls -la
total 24
drwxr-xr-x  2 root     root     4096 Jul 17 15:57 .
drwxr-xr-x 70 root     root     4096 Jul 17 15:58 ..
-rw-r--r--  1 root     root      220 Mar 31 08:41 .bash_logout
-rw-r--r--  1 root     root     3771 Mar 31 08:41 .bashrc
-r--------  1 bandit21 bandit21   33 Jul 17 15:57 .prevpass
-rw-r--r--  1 root     root      807 Mar 31 08:41 .profile
bandit21@bandit:~$ whoami
bandit21
bandit21@bandit:~$ cd /
bin/                formulaone/         lib.usr-is-merged/  proc/               srv/
bin.usr-is-merged/  home/               libx32/             root/               sys/
boot/               krypton/            lost+found/         run/                tmp/
dev/                lib/                media/              sbin/               usr/
drifter/            lib32/              mnt/                sbin.usr-is-merged/ var/
etc/                lib64/              opt/                snap/
bandit21@bandit:~$ cd /etc/cron.d
bandit21@bandit:/etc/cron.d$ ls
cronjob_bandit22  cronjob_bandit23  cronjob_bandit24  e2scrub_all  otw-tmp-dir  sysstat
bandit21@bandit:/etc/cron.d$ cat cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
bandit21@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
bandit21@bandit:/etc/cron.d$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
bandit21@bandit:/etc/cron.d$
```

## Notas Adicionales 
Cron Job en linux es una **herramienta que permite programar y ejecutar tareas específicas dentro de nuestro sistema operativo Linux de forma automática**
*/etc/cron.d * - ahi ponemos los cronjobs o dicho de otra forma los archivos que quieres que se ejecuten cada vez que prendes la computadora.
### Referencias
[[Guía completa de Cron Job en Linux para principiantes en 5 pasos (donweb.com)](https://guias.donweb.com/guia-completa-de-cron-job-en-linux/#:~:text=Cron%20Job%20en%20linux%20es,tiempo%20determinado%20por%20el%20usuario.)]


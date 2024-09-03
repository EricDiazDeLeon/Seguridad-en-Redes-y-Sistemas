## Objetivo 
The password for the next level is stored **somewhere on the server** and has all of the following properties:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size
## Datos de acceso al nivel 
bandit6
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

## Solución  
```bash
bandit6@bandit:~$ ls
bandit6@bandit:~$ find / -user bandit6 -size 33c
find: ‘/sys/kernel/tracing’: Permission denied
find: ‘/sys/kernel/debug’: Permission denied
find: ‘/sys/fs/pstore’: Permission denied
find: ‘/sys/fs/bpf’: Permission denied
find: ‘/snap’: Permission denied
find: ‘/run/lock/lvm’: Permission denied
find: ‘/run/systemd/inaccessible/dir’: Permission denied
find: ‘/run/systemd/propagate/systemd-udevd.service’: Permission denied
find: ‘/run/systemd/propagate/systemd-resolved.service’: Permission denied
find: ‘/run/systemd/propagate/systemd-networkd.service’: Permission denied
find: ‘/run/systemd/propagate/systemd-logind.service’: Permission denied
find: ‘/run/systemd/propagate/irqbalance.service’: Permission denied
find: ‘/run/systemd/propagate/chrony.service’: Permission denied
find: ‘/run/systemd/propagate/polkit.service’: Permission denied
find: ‘/run/systemd/propagate/ModemManager.service’: Permission denied
find: ‘/run/systemd/propagate/fwupd.service’: Permission denied
find: ‘/run/lvm’: Permission denied
find: ‘/run/log/journal/ec27119cecabde24cec12615c2a9a184’: Permission denied
find: ‘/run/cryptsetup’: Permission denied
find: ‘/run/multipath’: Permission denied
find: ‘/run/screen/S-bandit20’: Permission denied
find: ‘/run/screen/S-bandit25’: Permission denied
find: ‘/run/screen/S-bandit23’: Permission denied
find: ‘/run/screen/S-bandit19’: Permission denied
find: ‘/run/screen/S-bandit22’: Permission denied
find: ‘/run/screen/S-bandit18’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/run/user/11001’: Permission denied
find: ‘/run/user/11011’: Permission denied
find: ‘/run/user/11016’: Permission denied
find: ‘/run/user/11020’: Permission denied
find: ‘/run/user/11000’: Permission denied
find: ‘/run/user/11023’: Permission denied
find: ‘/run/user/11008’: Permission denied
find: ‘/run/user/11024’: Permission denied
find: ‘/run/user/11012’: Permission denied
find: ‘/run/user/11006/systemd/inaccessible/dir’: Permission denied
find: ‘/run/user/11005’: Permission denied
find: ‘/run/user/11004’: Permission denied
find: ‘/run/user/11013’: Permission denied
find: ‘/run/user/11025’: Permission denied
find: ‘/run/user/11014’: Permission denied
find: ‘/run/user/11002’: Permission denied
find: ‘/run/user/11007’: Permission denied
find: ‘/run/user/11015’: Permission denied
find: ‘/run/user/11021’: Permission denied
find: ‘/run/user/11010’: Permission denied
find: ‘/run/user/8004’: Permission denied
find: ‘/run/user/11026’: Permission denied
find: ‘/run/user/11032’: Permission denied
find: ‘/run/user/11003’: Permission denied
find: ‘/run/user/11027’: Permission denied
find: ‘/run/user/11029’: Permission denied
find: ‘/run/user/11022’: Permission denied
find: ‘/run/user/8002’: Permission denied
find: ‘/run/user/11033’: Permission denied
find: ‘/run/user/11030’: Permission denied
find: ‘/run/user/11009’: Permission denied
find: ‘/run/user/11028’: Permission denied
find: ‘/run/user/11019’: Permission denied
find: ‘/run/user/11031’: Permission denied
find: ‘/run/chrony’: Permission denied
find: ‘/run/udisks2’: Permission denied
find: ‘/boot/efi’: Permission denied
find: ‘/boot/lost+found’: Permission denied
find: ‘/home/drifter8/chroot’: Permission denied
find: ‘/home/bandit5/inhere’: Permission denied
find: ‘/home/bandit31-git’: Permission denied
find: ‘/home/bandit29-git’: Permission denied
find: ‘/home/ubuntu’: Permission denied
find: ‘/home/bandit30-git’: Permission denied
find: ‘/home/bandit28-git’: Permission denied
find: ‘/home/drifter6/data’: Permission denied
find: ‘/home/bandit27-git’: Permission denied
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/2394425/task/2394425/fd/6’: No such file or directory
find: ‘/proc/2394425/task/2394425/fdinfo/6’: No such file or directory
find: ‘/proc/2394425/fd/5’: No such file or directory
find: ‘/proc/2394425/fdinfo/5’: No such file or directory
find: ‘/drifter/drifter14_src/axTLS’: Permission denied
find: ‘/etc/stunnel’: Permission denied
find: ‘/etc/multipath’: Permission denied
find: ‘/etc/sudoers.d’: Permission denied
find: ‘/etc/credstore.encrypted’: Permission denied
/etc/bandit_pass/bandit6
find: ‘/etc/ssl/private’: Permission denied
find: ‘/etc/credstore’: Permission denied
find: ‘/etc/xinetd.d’: Permission denied
find: ‘/etc/polkit-1/rules.d’: Permission denied
find: ‘/root’: Permission denied
find: ‘/tmp’: Permission denied
find: ‘/lost+found’: Permission denied
find: ‘/dev/shm’: Permission denied
find: ‘/dev/mqueue’: Permission denied
find: ‘/var/spool/bandit24’: Permission denied
find: ‘/var/spool/rsyslog’: Permission denied
find: ‘/var/spool/cron/crontabs’: Permission denied
find: ‘/var/lib/udisks2’: Permission denied
find: ‘/var/lib/snapd/void’: Permission denied
find: ‘/var/lib/snapd/cookie’: Permission denied
find: ‘/var/lib/ubuntu-advantage/apt-esm/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/update-notifier/package-data-downloads/partial’: Permission denied
find: ‘/var/lib/amazon’: Permission denied
find: ‘/var/lib/chrony’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/polkit-1’: Permission denied
find: ‘/var/log/unattended-upgrades’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/log/amazon’: Permission denied
find: ‘/var/log/chrony’: Permission denied
find: ‘/var/tmp’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/pollinate’: Permission denied
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/apparmor/baad73a1.0’: Permission denied
find: ‘/var/cache/apparmor/2425d902.0’: Permission denied
bandit6@bandit:~$ find / -user bandit6 group bandit6 -size 33c
find: paths must precede expression: `group'
bandit6@bandit:~$ find / -user bandit7 group bandit6 -size 33c
find: paths must precede expression: `group'
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c
find: ‘/sys/kernel/tracing’: Permission denied
find: ‘/sys/kernel/debug’: Permission denied
find: ‘/sys/fs/pstore’: Permission denied
find: ‘/sys/fs/bpf’: Permission denied
find: ‘/snap’: Permission denied
find: ‘/run/lock/lvm’: Permission denied
find: ‘/run/systemd/inaccessible/dir’: Permission denied
find: ‘/run/systemd/propagate/systemd-udevd.service’: Permission denied
find: ‘/run/systemd/propagate/systemd-resolved.service’: Permission denied
find: ‘/run/systemd/propagate/systemd-networkd.service’: Permission denied
find: ‘/run/systemd/propagate/systemd-logind.service’: Permission denied
find: ‘/run/systemd/propagate/irqbalance.service’: Permission denied
find: ‘/run/systemd/propagate/chrony.service’: Permission denied
find: ‘/run/systemd/propagate/polkit.service’: Permission denied
find: ‘/run/systemd/propagate/ModemManager.service’: Permission denied
find: ‘/run/systemd/propagate/fwupd.service’: Permission denied
find: ‘/run/lvm’: Permission denied
find: ‘/run/log/journal/ec27119cecabde24cec12615c2a9a184’: Permission denied
find: ‘/run/cryptsetup’: Permission denied
find: ‘/run/multipath’: Permission denied
find: ‘/run/screen/S-bandit20’: Permission denied
find: ‘/run/screen/S-bandit25’: Permission denied
find: ‘/run/screen/S-bandit23’: Permission denied
find: ‘/run/screen/S-bandit19’: Permission denied
find: ‘/run/screen/S-bandit22’: Permission denied
find: ‘/run/screen/S-bandit18’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/run/user/11001’: Permission denied
find: ‘/run/user/11011’: Permission denied
find: ‘/run/user/11016’: Permission denied
find: ‘/run/user/11020’: Permission denied
find: ‘/run/user/11000’: Permission denied
find: ‘/run/user/11023’: Permission denied
find: ‘/run/user/11008’: Permission denied
find: ‘/run/user/11024’: Permission denied
find: ‘/run/user/11012’: Permission denied
find: ‘/run/user/11006/systemd/inaccessible/dir’: Permission denied
find: ‘/run/user/11005’: Permission denied
find: ‘/run/user/11004’: Permission denied
find: ‘/run/user/11013’: Permission denied
find: ‘/run/user/11025’: Permission denied
find: ‘/run/user/11014’: Permission denied
find: ‘/run/user/11002’: Permission denied
find: ‘/run/user/11007’: Permission denied
find: ‘/run/user/11015’: Permission denied
find: ‘/run/user/11021’: Permission denied
find: ‘/run/user/11010’: Permission denied
find: ‘/run/user/8004’: Permission denied
find: ‘/run/user/11026’: Permission denied
find: ‘/run/user/11032’: Permission denied
find: ‘/run/user/11003’: Permission denied
find: ‘/run/user/11027’: Permission denied
find: ‘/run/user/11029’: Permission denied
find: ‘/run/user/11022’: Permission denied
find: ‘/run/user/8002’: Permission denied
find: ‘/run/user/11033’: Permission denied
find: ‘/run/user/11030’: Permission denied
find: ‘/run/user/11009’: Permission denied
find: ‘/run/user/11028’: Permission denied
find: ‘/run/user/11019’: Permission denied
find: ‘/run/user/11031’: Permission denied
find: ‘/run/chrony’: Permission denied
find: ‘/run/udisks2’: Permission denied
find: ‘/boot/efi’: Permission denied
find: ‘/boot/lost+found’: Permission denied
find: ‘/home/drifter8/chroot’: Permission denied
find: ‘/home/bandit5/inhere’: Permission denied
find: ‘/home/bandit31-git’: Permission denied
find: ‘/home/bandit29-git’: Permission denied
find: ‘/home/ubuntu’: Permission denied
find: ‘/home/bandit30-git’: Permission denied
find: ‘/home/bandit28-git’: Permission denied
find: ‘/home/drifter6/data’: Permission denied
find: ‘/home/bandit27-git’: Permission denied
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/2396591/task/2396591/fd/6’: No such file or directory
find: ‘/proc/2396591/task/2396591/fdinfo/6’: No such file or directory
find: ‘/proc/2396591/fd/5’: No such file or directory
find: ‘/proc/2396591/fdinfo/5’: No such file or directory
find: ‘/drifter/drifter14_src/axTLS’: Permission denied
find: ‘/etc/stunnel’: Permission denied
find: ‘/etc/multipath’: Permission denied
find: ‘/etc/sudoers.d’: Permission denied
find: ‘/etc/credstore.encrypted’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
find: ‘/etc/credstore’: Permission denied
find: ‘/etc/xinetd.d’: Permission denied
find: ‘/etc/polkit-1/rules.d’: Permission denied
find: ‘/root’: Permission denied
find: ‘/tmp’: Permission denied
find: ‘/lost+found’: Permission denied
find: ‘/dev/shm’: Permission denied
find: ‘/dev/mqueue’: Permission denied
find: ‘/var/spool/bandit24’: Permission denied
find: ‘/var/spool/rsyslog’: Permission denied
find: ‘/var/spool/cron/crontabs’: Permission denied
find: ‘/var/lib/udisks2’: Permission denied
/var/lib/dpkg/info/bandit7.password
find: ‘/var/lib/snapd/void’: Permission denied
find: ‘/var/lib/snapd/cookie’: Permission denied
find: ‘/var/lib/ubuntu-advantage/apt-esm/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/update-notifier/package-data-downloads/partial’: Permission denied
find: ‘/var/lib/amazon’: Permission denied
find: ‘/var/lib/chrony’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/polkit-1’: Permission denied
find: ‘/var/log/unattended-upgrades’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/log/amazon’: Permission denied
find: ‘/var/log/chrony’: Permission denied
find: ‘/var/tmp’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/pollinate’: Permission denied
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/apparmor/baad73a1.0’: Permission denied
find: ‘/var/cache/apparmor/2425d902.0’: Permission denied
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```

## Notas Adicionales 
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
	/ indica a find que busque desde el directorio raiz
	-user indica a que usuario pertenece el archivo
	-group indica a que grupo pertence el archivo
	- 2>/dev/null manda la salida de error al dispositivo null, es deci, se oculta al usuario

### Referencias


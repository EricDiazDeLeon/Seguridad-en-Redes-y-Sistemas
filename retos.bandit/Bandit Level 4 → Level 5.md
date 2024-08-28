## Objetivo 
The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.
## Datos de acceso al nivel 
bandit4
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

## Solución 
cat * es un comodin para usar un comando con todos los archivos del directorio
```
PS C:\Users\Eric> ssh bandit4@bandit.labs.overthewire.org -p 2220
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit4@bandit.labs.overthewire.org's password:
Permission denied, please try again.
bandit4@bandit.labs.overthewire.org's password:
Permission denied, please try again.
bandit4@bandit.labs.overthewire.org's password:

      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * peda (https://github.com/longld/peda.git) in /opt/peda/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ ls -la
total 24
drwxr-xr-x  3 root root 4096 Jul 17 15:57 .
drwxr-xr-x 70 root root 4096 Jul 17 15:58 ..
-rw-r--r--  1 root root  220 Mar 31 08:41 .bash_logout
-rw-r--r--  1 root root 3771 Mar 31 08:41 .bashrc
drwxr-xr-x  2 root root 4096 Jul 17 15:57 inhere
-rw-r--r--  1 root root  807 Mar 31 08:41 .profile
bandit4@bandit:~$ cd inhere/
bandit4@bandit:~/inhere$ ls -la
total 48
drwxr-xr-x 2 root    root    4096 Jul 17 15:57 .
drwxr-xr-x 3 root    root    4096 Jul 17 15:57 ..
-rw-r----- 1 bandit5 bandit4   33 Jul 17 15:57 -file00
-rw-r----- 1 bandit5 bandit4   33 Jul 17 15:57 -file01
-rw-r----- 1 bandit5 bandit4   33 Jul 17 15:57 -file02
-rw-r----- 1 bandit5 bandit4   33 Jul 17 15:57 -file03
-rw-r----- 1 bandit5 bandit4   33 Jul 17 15:57 -file04
-rw-r----- 1 bandit5 bandit4   33 Jul 17 15:57 -file05
-rw-r----- 1 bandit5 bandit4   33 Jul 17 15:57 -file06
-rw-r----- 1 bandit5 bandit4   33 Jul 17 15:57 -file07
-rw-r----- 1 bandit5 bandit4   33 Jul 17 15:57 -file08
-rw-r----- 1 bandit5 bandit4   33 Jul 17 15:57 -file09
bandit4@bandit:~/inhere$ cat ./file00
cat: ./file00: No such file or directory
bandit4@bandit:~/inhere$ cat ./-file00
��,��␦����Yq��f�L���j␦�0����x�4Fbandit4@bandit:~/inhere$ cat ./-file01
N�.��bandit4@bandit:~/inhere$
bandit4@bandit:~/inhere$ cat ./-file02
��9������F��p������tk���%��bandit4@bandit:~/inhere$ cat ./-file03
�����n�Qy�y͍�{+R�bZ�k�F�*       bandit4@bandit:~/inhere$
bandit4@bandit:~/inhere$ cat ./-file04

l�����]�a߯-@gQ�÷�wz�P�ߠy�bandit4@bandit:~/inhere$ cat ./-file05
�pӻT9�F��3ˤ����)
T�՜F�ǭ�bandit4@bandit:~/inhere$ cat *
cat: invalid option -- 'f'
Try 'cat --help' for more information.
bandit4@bandit:~/inhere$ cat ./-*
N�.����9������F��p������tk���%�������n�Qy�y͍�{+R�bZ�k�F�*
l�����]�a߯-@gQ�÷�wz�P�ߠy��pӻT9�F��3ˤ����)
T�՜F�ǭ��QĹ�M���p4�-�8��=��!#g���4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
�$}P�cL��s��@�2%Y��(|�^��J
                  ы�Ϣ��bandit4@bandit:~/inhere$
bandit4@bandit:~/inhere$ cat ./-file07
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
bandit4@bandit:~/inhere$ file ./*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
bandit4@bandit:~/inhere$ cat ./-file07
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
bandit4@bandit:~/inhere$
```

## Notas Adicionales 

### Referencias


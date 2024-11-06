## Objetivo
The name of the game is [speed](https://www.youtube.com/watch?v=8piqd2BWeGI). Are you quick enough to solve this problem and keep it above 50 mph? [need-for-speed](https://jupiter.challenges.picoctf.org/static/cd51b2c95be9f3626db6fe6665afb5a3/need-for-speed).
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act23$ wget https://jupiter.challenges.picoctf.org/static/cd51b2c95be9f3626db6fe6665afb5a3/need-f  
or-speed  
--2024-11-06 11:01:37--  https://jupiter.challenges.picoctf.org/static/cd51b2c95be9f3626db6fe6665afb5a3/need-for-speed  
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8  
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 8888 (8,7K) [application/octet-stream]  
Grabando a: «need-for-speed»  
  
need-for-speed                   100%[========================================================>]   8,68K  --.-KB/s    en 0s         
  
2024-11-06 11:01:45 (142 MB/s) - «need-for-speed» guardado [8888/8888]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ ls  
chal.o  chal.s  gdbme  need-for-speed  test.S  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ file need-for-speed    
need-for-speed: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so  
.2, for GNU/Linux 3.2.0, BuildID[sha1]=6f1b99bffb980c293d03dd73bd458e6747c3c936, not stripped  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ chmod -x need-for-speed
kali@KaliEND:~/Downloads/PicoCTF/Act23$ ./need-for-speed    
bash: ./need-for-speed: Permiso denegado  
kali@KaliEND:~/Downloads/PicoCTF/Act23$ chmod 777 need-for-speed    
kali@KaliEND:~/Downloads/PicoCTF/Act23$ ./need-for-speed    
Keep this thing over 50 mph!  
============================  
  
Creating key...  
Not fast enough. BOOM!
kali@KaliEND:~/Downloads/PicoCTF/Act23$ gdb -q need-for-speed    
Reading symbols from need-for-speed...  
(No debugging symbols found in need-for-speed)  
(gdb) info functions  
All defined functions:  
  
Non-debugging symbols:  
0x00000000000005d8  _init  
0x0000000000000600  putchar@plt  
0x0000000000000610  puts@plt  
0x0000000000000620  alarm@plt  
0x0000000000000630  __sysv_signal@plt  
0x0000000000000640  exit@plt  
0x0000000000000650  __cxa_finalize@plt  
0x0000000000000660  _start  
0x0000000000000690  deregister_tm_clones  
0x00000000000006d0  register_tm_clones  
0x0000000000000720  __do_global_dtors_aux  
0x0000000000000760  frame_dummy  
0x000000000000076a  decrypt_flag  
0x00000000000007f1  calculate_key  
0x000000000000080e  alarm_handler  
0x000000000000082f  set_timer  
0x000000000000087d  get_key  
0x00000000000008ac  print_flag  
0x00000000000008d8  header  
0x000000000000091a  main  
0x0000000000000960  __libc_csu_init  
0x00000000000009d0  __libc_csu_fini  
0x00000000000009d4  _fini  
(gdb) set disassemble-flavor intel  
No symbol table is loaded.  Use the "file" command.  
(gdb) disassemble main  
Dump of assembler code for function main:  
  0x000000000000091a <+0>:     push   %rbp  
  0x000000000000091b <+1>:     mov    %rsp,%rbp  
  0x000000000000091e <+4>:     sub    $0x10,%rsp  
  0x0000000000000922 <+8>:     mov    %edi,-0x4(%rbp)  
  0x0000000000000925 <+11>:    mov    %rsi,-0x10(%rbp)  
  0x0000000000000929 <+15>:    mov    $0x0,%eax  
  0x000000000000092e <+20>:    call   0x8d8 <header>  
  0x0000000000000933 <+25>:    mov    $0x0,%eax  
  0x0000000000000938 <+30>:    call   0x82f <set_timer>  
  0x000000000000093d <+35>:    mov    $0x0,%eax  
  0x0000000000000942 <+40>:    call   0x87d <get_key>  
  0x0000000000000947 <+45>:    mov    $0x0,%eax  
  0x000000000000094c <+50>:    call   0x8ac <print_flag>  
  0x0000000000000951 <+55>:    mov    $0x0,%eax  
  0x0000000000000956 <+60>:    leave  
  0x0000000000000957 <+61>:    ret  
End of assembler dump.  
(gdb) set disassemble-flavor intel  
No symbol table is loaded.  Use the "file" command.  
(gdb) set disassembl  
disassemble-next-line  disassembler-options   disassembly-flavor        
(gdb) set disassembly-flavor intel  
(gdb) break *(main+40)  
Breakpoint 1 at 0x942  
(gdb) delete 1  
(gdb) breakpoints  
Undefined command: "breakpoints".  Try "help".  
(gdb) breakpoint  
Undefined command: "breakpoint".  Try "help".  
(gdb) break *(main+30)  
Breakpoint 2 at 0x938  
(gdb) run  
Starting program: /home/kali/Downloads/PicoCTF/Act23/need-for-speed    
[Thread debugging using libthread_db enabled]  
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".  
Keep this thing over 50 mph!  
============================  
  
  
Breakpoint 2, 0x0000555555400938 in main ()  
(gdb) jump *(main+35)  
Continuing at 0x55555540093d.  
Creating key...  
Finished  
Printing flag:  
PICOCTF{Good job keeping bus #24c43740 speeding along!}  
[Inferior 1 (process 4737) exited normally]

```
## Notas Adicionales

### Referencias
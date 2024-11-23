## Objetivo
Now for something a little different. `0x2262c96b` is loaded into memory in the `main` function. Examine byte-wise the memory that the constant is loaded in by using the GDB command `x/4xb addr`. The flag is the four bytes as they are stored in memory. If you find the bytes `0x11 0x22 0x33 0x44` in the memory location, your flag would be: `picoCTF{0x11223344}`.Debug [this](https://artifacts.picoctf.net/c/531/debugger0_c).
## Solución
```bash
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/gdbbaby3$ wget https://artifacts.picoctf.net/c/531/debugger0_c  
--2024-11-23 00:05:18--  https://artifacts.picoctf.net/c/531/debugger0_c  
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:6e00:16:5ec5:2840:93a1, 2600:9000:25ed:e600:16:5ec5:28  
40:93a1, 2600:9000:25ed:2c00:16:5ec5:2840:93a1, ...  
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[2600:9000:25ed:6e00:16:5ec5:2840:93a1]:443... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 16304 (16K) [application/octet-stream]  
Grabando a: «debugger0_c»  
  
debugger0_c                      100%[========================================================>]  15,92K  --.-KB/s    en 0s         
  
2024-11-23 00:05:18 (76,3 MB/s) - «debugger0_c» guardado [16304/16304]  
  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/gdbbaby3$ ls  
debugger0_c  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/gdbbaby3$ file debugger0_c    
debugger0_c: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, Bui  
ldID[sha1]=a10a8fa896351748020d158a4e18bb4be15cd3aa, for GNU/Linux 3.2.0, not stripped  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/gdbbaby3$ cat debugger0_c    
@@@@@�▒▒@▒@@@��@@��  @ @��P.P>@P>@��`.`>@`>@�88@8@ XX@X@DDS�td88@8@ P�td  @ @44Q�tdR�tdP.P>@P>@��/lib64/ld-linux-x86-64.so.2GNU�GN  
U�  
�N▒�K�\ӪGNU  
          ) libc.so.6__libc_start_mainGLIBC_2.2.5__gmon_start__u▒i     �?@�?@��H�H��/H��t��H����1�I��^H��H���PTI���@H��0@H��@��/�  
����f.���(@@H=(@@t�H��t �(@@��f��ff.�@�(@@H��(@@H��H��?H��H�H��t�H��t�(@@���ff.�@���=M/uUH���z����;/]Ð�ff.�@������UH���}�H�u��E�k�  
b"�E�]�f.�D��AWL�=-AVI��AUI��ATA��UH�--SL)�H������H��t1��L��L��D��A��H��H9�u�H�[]A\A]A^A_�ff.������H�H��0���LL���`���t,���������zR  
x  
0����D����  
RC  
Dd����eF�I▒�E �E(�D0�H8�G@n8A0A(B B▒B�����@�@  
�@P>▒X>���o�@�@                              @  
8  
▒h0    ▒���oH@���o���o@@`>@GCC: (Ubuntu 9.4.0-1ubuntu1~20.04.1) 9.4.0▒@8@X@|@�@�@@     H@  
h@  
 @  
�@ @ @8 @P>@X>@`>@�?@@@▒@@(@@▒��  
  
                               `@  
                                 �@!  
                                    �@7(@@FX>@m  
                                               @yP>@������� @���X>@�`>@�P>@� @�@@  
  
�@!@▒@@M \ @@i @x  
                0@e�0@@�  
                        P@F  
                            @/�(@@�  
                                   @@�  
                                      @crtstuff.cderegister_tm_clones__do_global_dtors_auxcompleted.8061__do_global_dtors_aux_fin  
i_array_entryframe_dummy__frame_dummy_init_array_entrydebugger0_c.c__FRAME_END____init_array_end_DYNAMIC__init_array_start__GNU_EH  
_FRAME_HDR_GLOBAL_OFFSET_TABLE___libc_csu_fini_edata__libc_start_main@@GLIBC_2.2.5__data_start__gmon_start____dso_handle_IO_stdin_  
used__libc_csu_init_dl_relocate_static_pie__bss_startmain__TMC_END__.symtab.strtab.shstrtab.interp.note.gnu.property.note.gnu.buil  
d-id.note.ABI-tag.gnu.hash.dynsym.dynstr.gnu.version.gnu.version_r.rela.dyn.init.text.fini.rodata.eh_frame_hdr.eh_frame.init_array  
.fini_array.dynamic.got.got.plt.data.bss.comment▒@▒#8@86X@X$I|@| W���o�@a  
� @ � @ 4�8 @8 �P>�X>�`>@`.��?@�@@�▒@@▒(@@(0(0+X0�▒▒    �5��7            �@�▒8q���o@@@~���oH@H�h@h▒�@ ���@�  
                                                            kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/gdbbaby3$
                                                            kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/gdbbaby3$ chmod +x debugger0_c  
kali@KaliEND:~/Downloads/PicoCTF/Exam3erParcial/gdbbaby3$ gdb debugger0_c  
GNU gdb (Debian 15.1-1) 15.1  
Copyright (C) 2024 Free Software Foundation, Inc.  
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>  
This is free software: you are free to change and redistribute it.  
There is NO WARRANTY, to the extent permitted by law.  
Type "show copying" and "show warranty" for details.  
This GDB was configured as "x86_64-linux-gnu".  
Type "show configuration" for configuration details.  
For bug reporting instructions, please see:  
<https://www.gnu.org/software/gdb/bugs/>.  
Find the GDB manual and other documentation resources online at:  
   <http://www.gnu.org/software/gdb/documentation/>.  
  
For help, type "help".  
Type "apropos word" to search for commands related to "word"...  
Reading symbols from debugger0_c...  
(No debugging symbols found in debugger0_c)  
(gdb) break main  
Breakpoint 1 at 0x40110e  
(gdb) Quit  
(gdb) disas main  
Dump of assembler code for function main:  
  0x0000000000401106 <+0>:     endbr64  
  0x000000000040110a <+4>:     push   %rbp  
  0x000000000040110b <+5>:     mov    %rsp,%rbp  
  0x000000000040110e <+8>:     mov    %edi,-0x14(%rbp)  
  0x0000000000401111 <+11>:    mov    %rsi,-0x20(%rbp)  
  0x0000000000401115 <+15>:    movl   $0x2262c96b,-0x4(%rbp)  
  0x000000000040111c <+22>:    mov    -0x4(%rbp),%eax  
  0x000000000040111f <+25>:    pop    %rbp  
  0x0000000000401120 <+26>:    ret  
End of assembler dump.
(gdb) break *0x000000000040111f
Breakpoint 2 at 0x40111f
(gdb) c
The program is not being run.
(gdb) start
Temporary breakpoint 3 at 0x40110e
Starting program: /home/kali/Downloads/PicoCTF/Exam3erParcial/gdbbaby3/debugger0_c 
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".

Breakpoint 1, 0x000000000040110e in main ()
(gdb) c
Continuing.

Breakpoint 2, 0x000000000040111f in main ()
(gdb) c
Continuing.
Breakpoint 3, 0x000000000040111f in main ()
(gdb) x/4xb $rbp-4
0x7fffffffda8c: 0x6b    0xc9    0x62    0x22
```
## Notas Adicionales
````
picoCTF{0x6bc96222}
````
### Referencias
## Objetivo 
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.
## Datos de acceso al nivel 
bandit19
cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
## Solución  
```bash
bandit19@bandit:~$ ls
bandit20-do
bandit19@bandit:~$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Jul 17 15:57 .
drwxr-xr-x 70 root     root      4096 Jul 17 15:58 ..
-rwsr-x---  1 bandit20 bandit19 14880 Jul 17 15:57 bandit20-do
-rw-r--r--  1 root     root       220 Mar 31 08:41 .bash_logout
-rw-r--r--  1 root     root      3771 Mar 31 08:41 .bashrc
-rw-r--r--  1 root     root       807 Mar 31 08:41 .profile
bandit19@bandit:~$ cat bandit20-do
ELFp4�54
         (444``���DD�� $�����DDP�tdL LL,,Q�tdR�td//lib/ld-linux.so.2GNU6�جF3�����G�PcMj�GGNU  �K��-S '_IO_stdin_usedexi>�����c_start_mainexecvprintflibc.so.6GLIBC_2.0GLIBC_2.34__gmon_start__4ii
    S�����/��������t�Ѓ[��5��%��%h������%������h������%
                                                      h����1�^����PTR���t/jjQV������P�����$���f�f�f�f�f�f�f��f�f�f�f�f�f�f���$�f�f�f�f�f�f��=t$���t���h�Ѓ���.��&��.��&��&�-���������t ���tU���Ph�҃��Ít&Í�&���=u���h�����Í�&Í�&��늍L$����q�U��Q���ȃ8 �@��P��������
                   j�����P�9��ph=��������M�ɍa��S��������.�[�

                                                            Run a command as another user.
  Example: %s id                     ����2zR|
env/usr/bin/env(�����$���Dd���p:����zR|     ���� 0H���F
                                                       J
                                                        tx?␦;*2$"(T����aD
                                                                         IuAu|N
                                                                               A�C
                                                                                  �P4
␦���o|�                                                                              �
      �
b
���aHN[ jy�������CC: (Ubuntu 13.2.0-23ubuntu4) 13.2.0� ��
  crt1.o__abi_tag__wrap_maincrtstuff.cderegister_tm_clones__do_global_dtors_auxcompleted.0__do_global_dtors_aux_fini_array_entryframe_dummy__frame_dummy_init_array_entrybandit20.c__FRAME_END___DYNAMIC__GNU_EH_FRAME_HDR_GLOBAL_OFFSET_TABLE___libc_start_main@GLIBC_2.34__x86.get_pc_thunk.bxprintf@GLIBC_2.0_edata_fini__data_start__gmon_start__exit@GLIBC_2.0__dso_handle_IO_stdin_usedexecv@GLIBC_2.0_end_dl_relocate_static_pie_fp_hw__bss_start__TMC_END___init.symtab.strtab.shstrtab.interp.note.gnu.build-id.note.ABI-tag.gnu.hash.dynsym.dynstr.gnu.version.gnu.version_r.rel.dyn.rel.plt.init.text.fini.rodata.eh_frame_hdr.eh_frame.init_array.fini_array.dynamic.got.got.plt.data.bss.comment�#��$6� D���o� N

                                                                                                          �
                                                                                                          pV||b^���o�k���o�0z� B$$� �  P�ppw��� J�LL ,�xx ��/�/��/��/�0�00&@0p 2��4bandit19@bandit:~$ ls
bandit20-do
bandit19@bandit:~$ ./bandit20-do  id
uid=11019(bandit19) gid=11019(bandit19) euid=11020(bandit20) groups=11019(bandit19)
bandit19@bandit:~$ ./bandit20-do  cat /etc/bandit_pass/bandit20
0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO

```

## Notas Adicionales 
setuid es un bit que se puede modificar en un ejecutable para darle permisos a un usuario especifico.
### Referencias


## Problem 1. Stratus IDE can not run the Sim Configs B in the first example "simple_p2p."
* Error Message:
```
Can't locate Env.pm in @INC (@INC contains: /usr/local/lib64/perl5 /usr/local/share/perl5 /usr/lib64/perl5/vendor_perl /usr/share/perl5/vendor_perl /usr/lib64/perl5 /usr/share/perl5 . /usr/cad/cadence/STRATUS/STRATUS_19.12.100/tools.lnx86/stratus/lib) at /usr/cad/cadence/STRATUS/STRATUS_19.12.100/tools.lnx86/stratus/lib/CynUtil.pm line 369.
```
* Solution: 
```
[root@msoc-r730 ~]# yum install perl-Env
```
## Problem 2. Stratus IDE can not run the synthesis because LD_LIBRARY_PATH Error.
* Error Message:
```
In Stratus IDE:
              #################################################################
              #                                                               #
  ERROR 02733:# Cannot start server, cmdesigner, see startup log at           #
  ERROR 02733.#   /home/roy/design/simple_p2p/bdw_work/modules/dut/BASIC/bdw_work/jobs/cmd_server/startup.log #
              #                                                               #
              #################################################################

In startup.log:

Starting Stratus DPOpt (Linux)
  Time: April 06, 2022. 11:17:01
  Host: msoc-r730
  User: roy
  Args: --dofile /usr/cad/cadence/STRATUS/STRATUS_19.12.100/share/stratus/tcl/bdw_cmd_shell.tcl --locallogfile /dev/null -x bdw_server_start
/usr/cad/cadence/STRATUS/STRATUS_19.12.100/tools.lnx86/cellmath/sbin/Linux/cynth-dpopt: symbol lookup error: /usr/lib64/libncurses.so.5: undefined symbol: _nc_putchar
```
* Solution: Do not source the license of other EDA tools.  
Since I sourced the license file of Verdi first, the corresponding verdi lib path is in LD_LIBRARY_PATH. This can be seen by ldd command:

1. With Verdi license sourced:
```
[roy@msoc-r730 ~]$ ldd /lib64/libncurses.so.5
        linux-vdso.so.1 =>  (0x00007ffdf87e9000)
        libc.so.6 => /lib64/libc.so.6 (0x00007f1cde4a2000)
        libdl.so.2 => /lib64/libdl.so.2 (0x00007f1cde29e000)
        libtinfo.so.5 => /usr/cad/synopsys/verdi/cur/etc/lib/libstdc++/LINUX64/libtinfo.so.5 (0x00007f1cde07d000)
        /lib64/ld-linux-x86-64.so.2 (0x00007f1cdea97000)
```
2. Without Verdi license sourced:
```
[roy@msoc-r730 ~]$ ldd /lib64/libncurses.so.5
        linux-vdso.so.1 =>  (0x00007ffe7751f000)
        libc.so.6 => /lib64/libc.so.6 (0x00007f59e47b0000)
        libdl.so.2 => /lib64/libdl.so.2 (0x00007f59e45ac000)
        libtinfo.so.5 => /lib64/libtinfo.so.5 (0x00007f59e4382000)
        /lib64/ld-linux-x86-64.so.2 (0x00007f59e4da5000)
```

## Problem 3. 
* Error Message:
```
```
* Solution:
```

```







# Modules
## Problem .
* Error Message:
```
```
* Solution:
```

```







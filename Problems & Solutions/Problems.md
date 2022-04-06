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
* How to install libncurses.so.5? 
```
yum install ncurses-devel
```
* Reference: [执行过程中，找不到指定的符号，报错退出的解决办法](http://www.lujun.org.cn/?p=4681)

## Problem 3. 
* Error Message:
```
In Stratus IDE:
              #################################################################
              #                                                               #
  ERROR 02366:# Error. See log file at /home/roy/design/simple_p2p/bdw_work/modules/dut/BASIC/logs/cyn_mux_estimate_config.log                                                  #
  ERROR 02366.#   . Synthesis engine reports error: can not find channel      #
  ERROR 02366.#   named "couldn't open socket: connection refused"            #
              #                                                               #
              #################################################################
              #################################################################
              #                                                               #
  ERROR 02390:# Data path optimization failed for test_mux_1_2 (error in      #
  ERROR 02390.#   internal part model).                                       #
              #                                                               #
              #################################################################
              #################################################################
              #                                                               #
  FATAL 02367:# An error occured in the synthesis of muxes.                   #
              #                                                               #
              #################################################################

        01445: Summary of messages of severity WARNING or greater:
        01193:   SEVERITY MSGID CNT
        01198:      FATAL 02367   1
        01198:      ERROR 02366   1
        01198:      ERROR 02390   1

stratus_hls failed with 3 errors and 0 warnings.

make[1]: *** [bdw_work/modules/dut/BASIC/dut_rtl.cc] Error 1
make: *** [hlsc_dut_BASIC] Error 2
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







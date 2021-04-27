# Learn strace Command

List all syscalls for a given command
```
strace ls /
strace cat file.txt
```


Summarize all syscalls for the touch command
```
strace -cw touch file.txt
```


```
root@node01:~# strace -cw touch file.txt
% time     seconds  usecs/call     calls    errors syscall
------ ----------- ----------- --------- --------- ----------------
 65.82    0.001317        1317         1           execve
  6.95    0.000139          35         4           openat
  5.00    0.000100          17         6           mmap
  4.90    0.000098          33         3           fstat
  4.85    0.000097          14         7           close
  3.55    0.000071          18         4           mprotect
  2.65    0.000053          18         3           brk
  2.40    0.000048          16         3         3 access
  1.10    0.000022          22         1           munmap
  0.85    0.000017          17         1           utimensat
  0.70    0.000014          14         1           read
  0.65    0.000013          13         1           arch_prctl
  0.60    0.000012          12         1           dup2
------ ----------- ----------- --------- --------- ----------------
100.00    0.002001                    36         3 total
```


ps aux | grep etcd
#get the pid in the ps aux output

strace -p 2334

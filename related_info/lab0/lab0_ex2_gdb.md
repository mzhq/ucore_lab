```
$ gcc -g -m32 -o lab0_ex2_gdb.out lab0_ex2_gdb.c
$ ./lab0_ex2_gdb.out
warning: this program uses gets(), which is unsafe.
Please input a string: abc
Segmentation fault: 11
```

得到了 Segmentation fault 错误，因为使用了未初始化的地址。


Program received signal SIGSEGV, Segmentation fault.
0x96b17e11 in gets () from /usr/lib/system/libsystem_c.dylib

## 教程

- [1] 运行 “gdb bugging” ，加载 bugging 可执行文件； $gdb bugging 
- [2] 执行装入的 bugging 命令； (gdb) run 
- [3] 使用 where 命令查看程序出错的地方； (gdb) where 
- [4] 利用 list 命令查看调用 gets 函数附近的代码； (gdb) list 
- [5] 在 gdb 中，我们在第 11 行处设置断点，看看是否是在第11行出错； (gdb) break 11 
- [6] 程序重新运行到第 11 行处停止，这时程序正常，然后执行单步命令next； (gdb) next 
- [7] 程序确实出错，能够导致 gets 函数出错的因素就是变量 string。重新执行测试程，“用 print 命令查看 string 的值； (gdb) run (gdb) print string (gdb) $1=0x0 
- [8] 问题在于string指向的是一个无效指针，修改程序，在10行和11行之间增加一条语句 “string=buff; ”，重新编译程序，然后继续运行，将看到正确的程序运行结果。

## 实际操作

- [6] (gdb) step
warning: this program uses gets(), which is unsafe.
Please input a string: abc

Program received signal SIGSEGV, Segmentation fault.
0x96b17e11 in gets () from /usr/lib/system/libsystem_c.dylib
- [7] (gdb) print string
$1 = 0x0
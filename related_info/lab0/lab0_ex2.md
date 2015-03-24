#README
Try below command
```
$gcc -g -m32 lab0_ex2.c
```
Then you will get a.out. Try to use gdb to debug lab0_ex2. 


---

```
$ gcc -g -m32 -o lab0_ex2.out lab0_ex2.c
$ ./lab0_ex2.out
Hello, world!
```

```
$ sudo gdb lab0_ex2.out
...
(gdb) l
1	#include <stdio.h>
2	int
3	main(void)
4	{
5	    printf("Hello, world!\n");
6	    return 0;
7	}
(gdb) break 5
Breakpoint 1 at 0x1f69: file lab0_ex2.c, line 5.
(gdb) run
...
Breakpoint 1, main () at lab0_ex2.c:5
5	    printf("Hello, world!\n");
(gdb) step
Hello, world!
0x977da6d9 in start () from /usr/lib/system/<libdyld class="dylib"></libdyld>
```

## 学到了

使用 GDB 调试的基础。

## 还不会

真实情况下使用 GDB 来调试。等真正使用的时候再来看。

## 问题解决

无法使用 gdb，似乎是 Mac 中的权限问题。

[osx - gdb fails with "Unable to find Mach task port for process-id" error - Stack Overflow](http://stackoverflow.com/questions/11504377/gdb-fails-with-unable-to-find-mach-task-port-for-process-id-error)
-> [code-signing.txt](http://www.opensource.apple.com/source/lldb/lldb-69/docs/code-signing.txt)

or -> [c++ - Emacs 24 and GDB 6.3 on Mac OS (Lion) - Stack Overflow](http://stackoverflow.com/questions/10221448/emacs-24-and-gdb-6-3-on-mac-os-lion)

- 在 Keychain 中做修改
- 或者直接给它 root 权限

临时使用 root 解决好了。

## 参考资料

- [用GDB调试程序（一） - 陈皓专栏　【空谷幽兰，心如皓月】 - 博客频道 - CSDN.NET](http://blog.csdn.net/haoel/article/details/2879)
- [用GDB调试程序（二） - 陈皓专栏　【空谷幽兰，心如皓月】 - 博客频道 - CSDN.NET](http://blog.csdn.net/haoel/article/details/2880)


## gcc 的参数

### `-S`

大意是编译完了不去汇编，而留下从 c 编译出来的 s 代码。

```
-S	Stop after the stage of compilation proper; do not assemble.  The
           output is in the form of an assembler code file for each non-
           assembler input file specified.

           By default, the assembler file name for a source file is made by
           replacing the suffix .c, .i, etc., with .s.

           Input files that don't require compilation are ignored. 
```

### `-g`

在可以使用 gdb 调试程序之前，必须使用 -g 或 –ggdb编译选项编译源文件。

运行 gdb 调试程序时通常使用如下的命令：

### `-m32` ？



#README
Try below command
```
$gcc -S -m32 lab0_ex1.c
```
Then you will get lab_ex1.S. Try to understand the content & relation of C file  and S file. 

---

## C 文件

前方定义全局变量，两个 int 变量，各自值为 1，还有一个大小为 10 的 int 数组。

然后是 main 函数，会被当做初始函数执行。main 函数里面执行的是一段内联汇编函数。含义未知。

## S 文件

分成了两段，指令段 (section pure_instruction) 和数据段 (section data)。

### 指令段

执行 main 函数先进性压栈，操作对应的寄存器。然后调用内联汇编函数。

内联汇编函数也是对应的操作堆栈，以及处理变量的值。

最后内联汇编函数结束，做对应的处理。

再之后 main 函数也结束。做对应的处理。

## 明白了的

- 有指令段和数据段之分
- C 语言里方便实现的函数需要在汇编中处理堆栈和寄存器

## 不明白

- 里面的不少命令还不大明白是什么意思
- 内联汇编函数的格式
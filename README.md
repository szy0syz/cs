# CS

> 自学 Computer Systems

## [Book]深入理解计算机系统

![image](https://user-images.githubusercontent.com/10555820/156911212-0661f43f-e093-4d9f-8502-68e06963c249.png)

华盛顿大学CSE351: The Hardware/Software Interface

产出目标：完成CSAPP书籍配套的所有Labs

> 这门课程是系统编程基础，也是后续操作系统/网络/数据库/编译等课程的基础，相关内容是通向系统架构师的基本功。这门课比较贴近企业实战，对动手能力要求很高，课程一大目标是要程序员写出对机器友好的高性能代码。

### Pre

> If you study and learn the concepts in this book, you will be on your way to becoming the rare power programmer who knows how things work and how to fix them when they break.
>
> 只是个前言，就说的那么厉害的样子 😂，如果变不成那么厉害该咋办？

### Ch01

GCC编译 `hello.c` 文件需执行如下四个阶段：`预处理阶段`、`编译阶段`、`汇编阶段`、`链接阶段`。

执行这四个阶段的程序(预处理器、编译器、汇编器、链接器)一起构成了整个编译系统。

- 预处理阶段：预处理器cpp根据以字符#开头的命令，修改原始C程序，将标准版的内容直接插入到该文本中，得到 `hello.i` 的文本
- 编辑阶段：编译器ccl将文本文件 `hello.i` 翻译成文本文件 `hello.s`，其包含一个汇编语言程序
- 汇编阶段：汇编器as将 `hello.s` 翻译成机器语言指令，并把这些指令打包成 `可重定位目标程序`，其文件为 `hello.o`，已经是一个二进制文件
- 链接阶段：扫描 `hello.o` 文件里的标准库函数调用，将例如 `printf.o` 的二进制文件合并到我们的 `hello.o` 文件里，这个过程就是由链接器ld负责合并的，最终我们就可以得到 `hello` 文件，它是一个 可执行目标文件，就可以背加载到内存中，由系统执行。

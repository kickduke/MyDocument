环境搭建（ubuntu默认已安装）

  * gcc   C编译器
  * gdb   C调试器
  * g++   C++编译器
  * make  工程编译工具
安装build-essential即可搭建C开发环境  



常用命令：

```
gcc -E hello.c       // 预处理
gcc -S hello.c       // 编译成汇编语言，生成.s文件
gcc -c hello.c       // 编译并汇编成机器码，生成.o文件
gcc -o hello hello.c // 编译汇编连接，生成可执行文件
gcc -static hello.c  // 强制静态连接，包含依赖的库文件，生成文件较大。默认动态连接
```


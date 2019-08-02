# 各种 make

![QQ截图20190802164920.png](https://i.loli.net/2019/08/02/5d43f91741e6425536.png)

## makefile
* 一个名为 makefile 的文件
* 用于自动化编译，链接工程(等同于VS2017等IDE的**生成**功能)
* 需要被 nmake.exe 或者 make.exe 来调用并生成应用程序

## NMake.exe
* 程序位置:在 Microsoft Studio 目录中检索 nmake.exe (添加到环境变量)
* 程序使用:使用命令行工具，移动到 makefile 所在目录，执行 nmake

## gcc
被 nmake.exe 和 make.exe 通过 makefile 来调用

## cmake
编写 CMakeList.txt ，然后用 cmake.exe 来生成 makefile

## 实例

![QQ截图20190802164757.png](https://i.loli.net/2019/08/02/5d43f91719ad182342.png)
![QQ截图20190802164851.png](https://i.loli.net/2019/08/02/5d43f91729ac481960.png) -》![QQ截图20190802164901.png](https://i.loli.net/2019/08/02/5d43f91730e0e61145.png)

### max.h

    int max(int a, int b);

### max.c

    #include "max.h"
    
    int max(int a, int b)
    {
        return a > b ? a : b;
    }

### max_num.c

    #include <stdio.h>
    #include <stdlib.h>
    #include "max.h"
    
    int main(void)
    {
        printf("The bigger one of 3 and 5 is %d\n", max(3, 5));
        system("pause");
        return 0;
    }

### makefile
    max_num.exe: max_num.o max.o
        gcc -o max_num.exe max_num.o max.o
    
    max_num.o: max_num.c max.h
        gcc -c max_num.c
    
    max.o: max.c max.h
        gcc -c max.c



# Windows安装GNU编译器使用makefile
## 下载 MinGW
下载后，运行程序：mingw-get-inst-20120426.exe，选择download latest repository catalogues. 选择编译器是勾选C 
Compiler
C++ Compiler
点击next进行下载及安装。

> 记得设置环境变量

## 编写c文件
* max.h(c程序头文件)
* max.c(c程序源文件)
* max_num.c(调用c程序:max)
* makefile()

## 使用 GCC 编译
cmd 到目录，输入 **make**
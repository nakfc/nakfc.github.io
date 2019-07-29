# 通过 vclinux 脚本将 makefile 生成 vcxproj


https://github.com/robotdad/vclinux

https://www.jianshu.com/p/3b1d04f49a7a

> 使用vs远程生成项目，这样就可以在vs中远程开发linux中的项目

1. 安装 Git 并使用其 Git Bash
2. 调用脚本 $ ./genvcxproj.sh 工程目录 xxx.vcxproj

    ./genvcxproj.sh H:/book-master/mmo/cli cli.vcxproj

3. 调用脚本 $ ./genfilters.sh 工程目录 xxx.vcxproj.filters

    ./genfilters.sh H:/book-master/mmo/cli cli.vcxproj.filters


## instance-window-dev
* ip：35.203.187.8
* 端口：22
* 用户名：rsa-key-20181205
* 凭据：F:\0.1.Key\rsa-key-20181205.ppk

## 安装 gcc g++
yum install gcc
yum install gcc-c++

## 错误1
严重性	代码	说明	项目	文件	行	禁止显示状态
错误		cannot find -ldynamic_library	ConsoleApplication1	C:\usr\bin\ld	1	
错误		cannot find -lstatic_library	ConsoleApplication1	C:\usr\bin\ld	1	
错误		ld returned 1 exit status	ConsoleApplication1	C:\Users\3F\source\repos\SolutionMake\ConsoleApplication1\collect2	1	

~/projects/bin/$(Platform)/$(Configuration)

> 解决方案(Id找不到路径：ld --verbose) 命令行增加  

-Wl,-L"/home/rsa-key-20181205/projects/bin/x64/Debug" 
# 通过 vclinux 脚本将 makefile 生成 vcxproj


https://github.com/robotdad/vclinux

https://www.jianshu.com/p/3b1d04f49a7a

> 使用vs远程生成项目，这样就可以在vs中远程开发linux中的项目

1. 安装 Git 并使用其 Git Bash
2. 调用脚本 $ ./genvcxproj.sh 工程目录 xxx.vcxproj

    ./genvcxproj.sh H:/book-master/mmo/cli cli.vcxproj

3. 调用脚本 $ ./genfilters.sh 工程目录 xxx.vcxproj.filters

    ./genfilters.sh H:/book-master/mmo/cli cli.vcxproj.filters


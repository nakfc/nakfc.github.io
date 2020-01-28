
# One  

5.每天一个 HelloWorld
6.stub中肯定会提供相关的实现【父类】供访问远程实例
(客户端中gRPC是Greeter.GreeterClient，VCE是k_proto_client)
(服务端中gRPC是？，VCE是k_proto_server)
7.【父类】函数的格式是固定的(废话，因为是根据IDL自动生成的)
7.1.VCE中会增加前缀
IDL方法:signup
stub的Client方法:【①send_signup】(climain)
stub的Server方法:【②recv_signup】(sv)->【send_put_Player】(sv)->【recv_put_Player】(dbsvmain)->【send_put_Player_result】(dbsvmain)->【recv_put_Player_result】(gmsvmain)->【send_signupResult】(gmsvmain)->【recv_signupResult】(climain)->ok!233

7.2.gRPC中
一模一样，定义的方法是 SayHello
那么Server和Client都是 SayHello


1.添加版本控制
2.使用values的字符串，出版本
3.只更改广告ID，出版本1
4.


Q:怎么把makefile文件和C++源代码转成VS工程？
A1:在VS的命令行环境里面nmake
A2:
空项目 添加
生成命令行：nmake -f Makefile.nmake all
重新生成命令行：nmake -f Makefile.nmake all
清除命令行：nmake –f Makefile.nmake distclean
输出（用于调试）：输出路径


Q:qt程序无法运行
A:
F:\Qt\Qt5.8.0\5.8\mingw53_32\bin和
F:\Qt\Qt5.8.0\Tools\QtCreator\bin这个路径

Q:本地NuGet包下载的路径
A:C:\Users\Administrator\.nuget\packages


I:只要定义【Continuous deployment rtigger】 一旦 push 仓库，Pipelines 就直接出版本到目标 agent  
I:Builds 一旦生成，基本不用再动，前提是选择正确的 pipeline，【ASP.NET】【ASP.NET CORE】【.NET Desktop】  
I:注意 Releases 中 Agent job 的 task，要选择能正确编译构建项目的 task。例如【Build solution **\*.sln】  

Q:无法在Bolt的FlowMachine中指定需要使用的组件（如：Text.text(set)）  
A1:因为处于独立的Macro模式下，无法调用其他组件，需要设置为内嵌模式 Macro->Embed  
A2:任何独立的Macro如果需要调用外部组件，则必须先在Macro的变量处设置变量并且指定外部组件，然后在Flow内部通过GetVariable来实现调用  
![GIF 2019-11-12 19-34-48.gif](https://i.loli.net/2019/11/12/BDC5FG3R2TP1sVH.gif)  

# Two
# Three

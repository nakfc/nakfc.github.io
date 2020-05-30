

主页:https://azure.microsoft.com/zh-cn/services/devops/

# Azure Boards
> 团队协作敏捷工具

Work item process
* Agile(敏捷)

采用的是迭代式开发.

一、敏捷开发技术的适用范围:
1.项目团队的人数不能太多
2.项目经常发生变更
3.高风险的项目实施
4.开发人员可以参与决策
优势：
敏捷确实是项目进入实质开发迭代阶段，用户很快可以看到一个基线架构版的产品。敏捷注重市场快速反应能力，也即具体应对能力，客户前期满意度高。


## WorkItems(工作项目)
    * 创建,修改,
* Bug()
* Epic(叙事)
    * 打算做***的功能
    * 不涉及具体需求
* Feature(特性)
    * 具体要做的事
    * 作为 child 添加到 Epic
* Issue(疑问)
    * 对父类型发出的疑问
* Task(任务)
    * 工作具体的执行事项
* Test Case(测试事件)
    * 未知
* User Story(用户需求)
    * 用户的需求，一般由用户填写

Boards:
Backlogs:项目需求
Sprints:交付的迭代产品
Queries:


* Basic
* CMMI
* Scrum

![20171006001045274.png](https://i.loli.net/2019/07/13/5d297927048b048180.png)

# Azure Pipelines
> 适用于任何语言,平台和云的 CI/CD 生成，测试和部署。连接到Git程序并提供持续部署

# Azure Repos
> 无限 Git 存储库

# Azure Test Plans
> 提供手动测试和探索测试工具

# Azure Artifacts
> 创建，托管和共享包(D:\OneDrive\z.NuGet)

maven:java
nuget:.net
pip:python
npm:js

* Push Packages using NuGet.exe
    1. Download CredentialProviderBundle.zip
    2. Add this feed
        nuget.exe sources Add -Name "409588457" -Source "https://pkgs.dev.azure.com/409588457/_packaging/409588457/nuget/v3/index.json"
    3. Push a package(注意，创建的 feed 必须 【Only use packages published to this feed】，否则若上传已有的包，会提示已经有较高的版本)
        nuget.exe push -Source "409588457" -ApiKey AzureDevOps my_package.nupkg


>       :: 增加 feed
>       pause
>       nuget.exe sources Add -Name "Yukihoho" -Source "https://pkgs.dev.azure.com/409588457/_packaging/Yukihoho/nuget/v3index.json"
>       :: 提交本地包
>       nuget.exe push -Source "Yukihoho" -ApiKey AzureDevOps google.protobuf.3.9.0.nupkg
>       pause
>       nuget.exe push -Source "Yukihoho" -ApiKey AzureDevOps grpc.1.22.0.nupkg
>       pause
>       nuget.exe push -Source "Yukihoho" -ApiKey AzureDevOps grpc.tools.1.22.0.nupkg
>       pause


# 其他工具
构建工具
Java-Apache/Maven/Ant

持续继承框架
 持续继承共:Jenkins
 代码质量分析工具:Sonar 
 核心:编译，代码检查，测试，部署，反馈

 


## 增加 Self-hosted Windows agents
> 为了在本地运行编译好的程序

![3.png](https://i.loli.net/2019/07/17/5d2f1ae28295196186.png)

### windows下运行管理员PowerShell

https://dev.azure.com/409588457/Bakura/_machinegroup

![QQ截图20190717200452.png](https://i.loli.net/2019/07/17/5d2f0f91e5a8412486.png)

完成以后，显示一个目标主机已经上线

![QQ截图20190717200722.png](https://i.loli.net/2019/07/17/5d2f0f91de87273140.png)

### 查看当前 Pipelines 的管道数量，添加到 agent pool(免费版本只能增加一个)

https://dev.azure.com/409588457/Bakura/_settings/buildqueue?_a=concurrentJobs

![QQ截图20190717202517.png](https://i.loli.net/2019/07/17/5d2f13bacd17412865.png)

### 有可能的其他流程

To build and deploy windows solutions.Need one Windows agent.

When setup asks for your server URL, for Azure DevOps Services, answer https://dev.azure.com/{your-organization}.
https://dev.azure.com/409588457/Bakura

When setup asks for your authentication type, choose PAT. Then paste the PAT token you created into the command prompt window.
7zvk4oe45t6htxhnpr53sb53vbpgtg3bq555eetwazkehidmcswa

Run the agent
If you configured the agent to run interactively, to run it:
ps
复制
.\run.cmd

## Releases 新增流程(Self-hosted)

![1.png](https://i.loli.net/2019/07/17/5d2f15a75a50d69476.png)

### 为 agent job 增加一个或者多个 task(任务作业)
> task 通常是 Build CMake npm 之类
![2.png](https://i.loli.net/2019/07/17/5d2f15a790a7f53946.png)

### 这里增加了一个任务，在 .net 中对所有 .csproj 进行构建

    **/*.csproj

![QQ截图20190717202933.png](https://i.loli.net/2019/07/17/5d2f14b99b0c925467.png)


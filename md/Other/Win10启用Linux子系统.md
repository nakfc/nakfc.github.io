0. 安装 Windows 应用商店
* Windows Powershell
* 获取所有安装包 
Get-AppxPackage -allusers | Select Name, PackageFullName
* 安装
Add-appxpackage -register "C:\Program Files\WindowsApps\Microsoft.WindowsStore_11905.1001.4.0_x64__8wekyb3d8bbwe\appxmanifest.xml" -disabledevelopmentmod

Microsoft.WindowsStore_11905.1001.4.0_x64__8wekyb3d8bbwe

1. 控制面板  
Win+R control

2. 启用功能:使用与 Linux 的 Windows 子系统
在【启用或关闭 Windows 功能】中勾选

3.  
更新和安全-开发者选项


搜索 Linux
# 1.Welcome to the Course
# 2.Interface & Navigation(界面与导航)
## 默认界面
> 默认界面有标题栏和4个视图窗口(鼠标指向标题栏可以滚动)  
![01.默认窗口.png](https://i.loli.net/2020/05/09/7NDbk9XeFKpthOg.png)  
1. 3D视图
2. 大纲视图
3. 时间线
4. 属性
## 拆分窗口  
> 右键窗口边界可以新增窗口(需要删除的时候用合并即可)  
![02.拆分窗口.png](https://i.loli.net/2020/05/09/G2LfiTKnHBSjhzM.png)  

## 快捷键
### 物体模式快捷键
* W 改变游标行为(移动/选择模式)
* T/N 展开左边和右边的工具条

## 窗口模式
不同的窗口模式用于不同的工作流，如物体模式用于检视，编辑模式用于编辑
## 视图着色方式  
> 线框/实体/材质/渲染  
![03.视图着色方式.png](https://i.loli.net/2020/05/09/fJIv14nFLWwMGhZ.png)  

## 旋转视图
* 鼠标中键旋转/点击XYZ（Shift+鼠标中建 手掌平移）
* 小键盘按键“.” **选中居中**
* 按键“Home” **全部选中居中**

# 3.Organic Modeling & 04 - Hard-Surface(有机苹果)

# 窗口：3D视图


# 4.Organic Modeling & 04 - Hard-Surface()
## 应用操作
* 设置物体的实际尺寸(通常是cm)    
![04.物体的实际尺寸.png](https://i.loli.net/2020/05/09/U7Q5SyTgVjzOtk8.png)  

* 应用缩放：Ctrl+A，然后应用缩放  
![05.应用缩放.png](https://i.loli.net/2020/05/09/YsyT3kEiBVRHdPG.png)  

* 高级缩放:按下S键后，可以继续点击X,Y,Z针对其轴缩放
* 顶点合并:将多余的顶点按照距离等规则合并，避免以后误操作  
![07.顶点合并.png](https://i.loli.net/2020/05/09/ZPujSRehdqgBwcp.png)  

## 快捷键
Tab:切换物体模式/编辑模式
数字1/2/3:点线面切换

游标:Shift+空格,空格
环选：w，选中线，Alt+单击

移动:Shift+空格,G
缩放:Shift+空格,S
旋转:Shift+空格,R

挤出:Shift+空格,E

环切:Shift+空格,Ctrl+R
> 把一段分隔成多段

旋转归零:选中对象后，Alt+R
坐标归零:选中对象后，Alt+G
复制物体:选中对象后，Shift+D

## 刀建模

## 设置透明的图像参考
![06.设置透明的图像参考.png](https://i.loli.net/2020/05/09/IL39ebYgOplBKma.png)  

# 5.Cloth Simulation(布料模拟)
Timestamps:

00:00 - Introduction
00:41 - Bowl modeling
04:19 - Bowl modifier
07:11 - Wooden planks modeling
09:52 - Cloth simulation
15:31 - Outro

## 缩放S以及移动G时可以锁定XYZ轴
制造底部平面:S-Z-Num0

## 布料以及物理计算
1.为布料，地表，碰撞物增加物理属性
2.在动画模式下完成动画，然后应用修改器(修改器会被失去表示应用到对象)

# 6.UV
## UV 展开

Timestamps:

00:00 - Introduction
00:32 - UV unwrapping explained（UV展开解释）
01:36 - Apply scale
02:11 - Prepare UV unwrapping
04:47 - Apple mark seams（缝接）
06:01 - Apple UV unwrapping and UV map adjustments（调整）
08:35 - Knife mark seams and UV unwrapping
11:15 - Outro

## UV展开&纹理绘制
在纹理绘制前需要展开UV，纹理绘制可以使用**材料属性**进行印制，也可以手动绘制
## 1.UV展开（编辑模式）
1. 手动展开    
    进入UV Editing界面，手动UV展开，Shift+alt+单击选中需要分隔的边，右键->标记缝合边，点击UV，点击展开
2. 自动展开  
    进入UV Editing界面，A全选，点击UV，点击**智能UV投射**

## 2.纹理绘制-手动绘制（绘制模式）
1. 默认显示**粉色**，表示没有任何材质与图像
2. 在左边窗口创建一个基础图像
3. 纹理槽选择**单张图像**连接到新建的图像（按F，然后移动鼠标可以改变画笔半径）
## 3.纹理绘制-印制绘制（绘制模式）
1. 在**纹理属性**选择新建，在图像->设置中打开需要印制的图像（现在可以预览到需要印制的图像）  
![QQ截图20200514173443.png](https://i.loli.net/2020/05/14/u1i2wXCmg4a6qBU.png)
2. 返回到**活动工具与工作区**，在笔刷设置->纹理中选择纹理，然后在**映射**中选择**镂版**（然后此时就可以进行印制）
    > 右键移动镂版，Shift+右键缩放镂版
![QQ截图20200514174105.png](https://i.loli.net/2020/05/14/BlzJ7rsak5V8qLF.png)  


## 要点
* 纹理绘制中**无法绘制**:Tab，A，Tab（返回编辑模式选中所有物体，然后再返回纹理绘制）
* 绘制的时候绘制到了**背面**:Tab,Shift+N,Tab（返回编辑模式，从新计算法线后返回纹理绘制）
* 使用已经存在的材质，会导致原本的材质同时改动，注意选择**新建材质**    
![QQ截图20200514223154.png](https://i.loli.net/2020/05/14/o8CbXBUMZ2DszLn.png)  


## 版本改动
* 现在Texture属于Brush下(原本是同级)


## 09.材质-Material
## Procedural Materials
> 程序化生成的材质
## 快速添加Material节点
* 转换器色带
    ColorRamp:Shift+A->N->O
* 凹凸图
    Bump:Shift+A->V+B
    粗糙度，由灰度定义高度

* 纹理坐标节点
    Texture Coordinate:Shift+A->I->X
* 映射节点
    Mapping:Shift+A->V-M
* 色相/饱和度节点
    Hue/Saturation:Shift+A->C->H
    调节色相/饱和度/亮度

## 10.透明纹理-Transparent Textures
* 法线贴图
    NormalMap:
    用不同的颜色定义高度（类似于凹凸贴图）



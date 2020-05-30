# UV 展开

Timestamps:

00:00 - Introduction
00:32 - UV unwrapping explained（UV展开解释）
01:36 - Apply scale
02:11 - Prepare UV unwrapping
04:47 - Apple mark seams（缝接）
06:01 - Apple UV unwrapping and UV map adjustments（调整）
08:35 - Knife mark seams and UV unwrapping
11:15 - Outro

# UV展开&纹理绘制
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


# 09.材质-Material
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

# 10.透明纹理-Transparent Textures
* 法线贴图
    NormalMap:
    用不同的颜色定义高度（类似于凹凸贴图）


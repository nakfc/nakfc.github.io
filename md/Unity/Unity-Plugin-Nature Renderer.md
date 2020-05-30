# 使用
* 更好看的草，树木，风？只需要增加一个组件即可？ **Nature Renderer**


# Unity Terrain Engine
## 
添加:GameObject->3D Object->Terrain
![](https://docs.unity3d.com/2019.1/Documentation/uploads/Main/1.1-TerrainInspector.png)
> 自动创建对象:Terrain，并拥有3个组件:Transform,Terrain,Terrain Collider

1. 创建相邻的地形土块(Create Neighbor Terraisn)
    * 
2. 雕刻并绘制地形
    * 升高或降低地形
    * 绘制洞
    * 绘制图像
    * 设置高度：将高度图调整为特定值。
    * 平滑高度：平滑高度图以软化地形特征。
    * 标记地形：在当前高度图的顶部标记画笔形状。

3. 添加树
4. 添加细节，如草，花朵岩石
5. 常规设置

## Terrain Layers
> 有关地形的创建，属性等详细信息
https://docs.unity3d.com/2019.1/Documentation/Manual/class-TerrainLayer.html

1. 反射图(Diffuse,Albedo)
> 主贴图
2. 法线贴图(Normal Map)
> normalmap要改type为Normalmap类型才能用
3. TerrainLit shader(Mask Map,用于HDRP)
> 应该是在HDRP才有作用的Shader

# 
Nature Renderer 取代预设的 Unity地形细节渲染系统，并作用在您原有的数据上。 一样的草木植被，保留您原有的地形。我们只是渲染得更好更快！



# 文档
https://assetstore.unity.com/packages/tools/terrain/nature-renderer-153552

https://support.visualdesigncafe.com/hc/zh-cn/articles/360000498661-%E5%9C%A8%E6%82%A8%E7%9A%84%E5%9C%BA%E6%99%AF%E5%9C%B0%E5%BD%A2%E5%90%AF%E5%8A%A8Nature-Renderer
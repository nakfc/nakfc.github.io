# 基础知识回顾
## Unity Shader & Unity Material
1. Unity Shader:一段代码(.shader),用于告知GPU如何绘制颜色.
2. Unity Materials:材质(.mat),
    * 某场景使用了一个材质球作为天空盒,材质球使用一个立方体贴图Cubemap(HDR)
        * 材质球:TCP2_Demo_SkyboxDay
        * 贴图文件:TCP2_Demo_CubemapDay.png

# 
使用Shaders和脚本来给与游戏 **Stylized look** 程序化外观
主要工作流分为两种
1. **Physically-Based Shaders** based on Unity's Standard shader
> 基于Unity标准Shader的PBS(基于物理Shader)


2. **"Legacy"** Shaders based on the shaders before Unity 5 (using Lambert diffuse and Blinn-Phong specular models)
> Legacy旧版Shader

## Shaders的两种主要功能
1. a set of shaders with a **Unified Material Inspector**: you only select the base Shader in Unity and TCP2 handles selecting the correct one depending on the options you toggle
> **统一材质监视器**:提供一个检视窗口来设置Shader

2. the **Shader Generator** allowing you to generate your own Unity shader, with even more features available than in the unified shader
> **Shader生成器**:生成高级Shaders(Shader Generator 2 已经在开发中，将会取代，同时支持LWRP(Lightweight Pipeline))
> 打开窗口:Tools->Toony Color Pro->Shader Generator


# 文档
https://jeanmoreno.com/unity/toonycolorspro/Documentation/
https://jeanmoreno.com/unity/toonycolorspro/Documentation/#pbs_shader

# 
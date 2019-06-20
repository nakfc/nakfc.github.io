# Unity
## 1.Transform [doc:Transform](https://docs.unity3d.com/2019.1/Documentation/Manual/class-Transform.html)
> The Transform **component** determines the Position, Rotation, and Scale of each object in the scene
. Every GameObject
has a Transform.

![](https://docs.unity3d.com/2019.1/Documentation/uploads/Main/TransformExample1.png)

## 2.Mesh Filter [doc:Mesh Filter](https://docs.unity3d.com/2019.1/Documentation/Manual/class-MeshFilter.html)
The **Mesh Filter** takes a mesh from your assets and passes it to the Mesh Renderer for rendering on the screen.
> To see the Mesh in your scene,add a **Mesh Renderer** to the GameObject.

![](https://docs.unity3d.com/2019.1/Documentation/uploads/Main/Inspector-MeshFilter.png)

## 3.Mesh Renderer [doc:Mesh Renderer](https://docs.unity3d.com/2019.1/Documentation/Manual/class-MeshRenderer.html)
The **Mesh Renderer** takes the geometry from the **Mesh Filter** and renders it at the position defined by the GameObject's **Transform** component.

![](https://docs.unity3d.com/2019.1/Documentation/uploads/Main/class-MeshRenderer-0.png)

## 4.Canvas [doc:Canvas](https://docs.unity3d.com/2019.1/Documentation/Manual/class-Canvas.html)


![QQ截图20190618194906.png](https://i.loli.net/2019/06/18/5d08cfc8077d560932.png)

## 6.Image

Sliced:切片
Tiled:平铺(拼贴)
Filled:填充

![](https://docs.unity3d.com/2019.1/Documentation/uploads/Main/UI_ImageInspector.png)



## 创建简单Image动画

+ GameObject 增加组件 Image
+ GameObject 增加组件 Animator
+ 选中 GameObject 按键 Ctrl + 6
+ 为 GameObject 创建 Clip(片段) 并保存。(这里Animator会自动绑定新建的Clip)

点击红色按钮进行录制
+ 1.选择时长
+ 2.选择动作 点击GO，点击Image-Fill Amount 改为1(原本为0)
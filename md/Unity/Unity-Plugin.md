# Package Manager
## FBX Exporter(preview)
* 此包用于导出fbx，预览包
* https://docs.unity3d.com/Packages/com.unity.formats.fbx@3.0/manual/exporting.html
### 导出FBX:GameObject->Export To FBX
* 即可
# Asset Store
## Find Reference 2 - 
* 查找资源的依赖关系(引用了哪些资源，被那些资源引用)
* 减少构建大小
## Voxel Importer
* 导入体素然后可以直接编辑
* 为各个部位添加重量，然后指定为Humanoid
* 指定Animation Controller即可直接运行对应动作
![](![GIF 2020-2-15 0-05-02.gif](https://i.loli.net/2020/02/15/TwgiYs7Xrp6hQOE.gif))  

## MagicVoxel To Unity
* 将vox和qb格式转换为Prefab或obj等文件
* https://assetstore.unity.com/packages/tools/modeling/magicavoxel-to-unity-63336
### MagicVoxel模型可以直接用此插件添加骨骼(2.2.0)
* 骨骼编辑器可以用来为模型添加骨骼，绘制权重，并创建带有相应组件的 Prefab。操作简单合理，让你享受创作的过程。

### 一键生成地图
* : 随机生成一张地图然后保存成vox文件。
### 一键生成角色
* : 创建体素角色，导出 vox 文件和带有 avatar 的 Prefab。

### 创建 Prefab
* 用内置的FBX导出器导出的fbx，会绑定此Prefab，若删除Prefab，则fbx会丢失贴图，原因不明
![QQ截图20200213173040.png](https://i.loli.net/2020/02/14/ihVtj7KxNXkR3yZ.png)
### 创建 LOD Prefab
![QQ截图20200214164512.png](https://i.loli.net/2020/02/14/LVMNGtzxvUc6hFg.png)  
### 创建 Obj
![QQ截图20200214164729.png](https://i.loli.net/2020/02/14/ihdsNVSy8C123D6.png)
### 创建 Sketch Sprite
![QQ截图20200214164918.png](https://i.loli.net/2020/02/14/mIMp4f31Ts8qtLY.png)
### 创建 8bit Sprite
![QQ截图20200214164950.png](https://i.loli.net/2020/02/14/lgQtbkws8PVBWi7.png)

## UMotion
### 任意模型动画编辑器
* 商店:https://assetstore.unity.com/packages/tools/animation/umotion-pro-animation-editor-95991  
* 手册:file:///D:/00.UnityProject/2019.3.0f6-Temp/Assets/UMotionEditor/Manual/pages/GettingStarted.html  

### 动画片段创建-Humonoid
* 创建模型对应的动画类型项目 
    * Clip Editor->File->NewProject->Humonoid
* 选取模型到Pose Editor  
* 设置IK
    * 切换模式 Config Mode
    * 点击 IK Setup Wizard
    * 点击 ok
    * 点击 create
* 移动骨骼
    * 切换到 Pose Editor -> Pose Editor
    * 在 Pivot 选择 Global
    * 在 Tool 选择 Move
* 保存
* file:///D:/00.UnityProject/2019.3.0f6-Temp/Assets/UMotionEditor/Manual/pages/QuickStart.html

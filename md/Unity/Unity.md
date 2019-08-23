# 快捷键
|功能|快捷键|
|:---|:---:|
|Scene|Ctrl+1|
|Game|Ctrl+2|
|Inspector|Ctrl+3|
|Hierarchy|Ctrl+4|
|Project|Ctrl+5|
|Animation|Ctrl+6|
|Profiler|Ctrl+7|
|ParticleEffect|Ctrl+8|
|AssetStore|Ctrl+9|
|AssetServer|Ctrl+0|

|功能|快捷键|
|:---|:---:|
|Console|Ctrl+Shift+c|

|功能|快捷键|
|:---|:---:|
|保存选择|Ctrl+Alt+1-9|
|载入选择|Ctrl+Shift+1-9|

|功能|快捷键|
|:---|:---:|
|复制对象|Ctrl+D|
|定点捕捉|V|

# 操作
* Alt + 左键 ： 摄像机以地面为中心旋转
* Alt + Ctrl + 左键 ： 摄像机平行移动
* 制作预设体Prefabs:从**Hierarchy**中拖动到**Project**中
* 预设体独立到实体:右键选择->**Unpack Prefab**

> 红色代表X轴，绿色代表Y轴，蓝色代表Z轴
![QQ截图20190604211833.png](https://i.loli.net/2019/06/04/5cf66fbcc351d97518.png)


# 脚本
## 示例脚本
		using UnityEngine;
		using System.Collections;
		using System.Collections.Generic;

		public class AlienSpaceship:MonoBehaviour{
			
			// 公共变量值显示在 Inspector (可编辑)
			public string ShipName;

			// 私有变量值显示在 Inspector (无法编辑)
			[SerializeField]
			private string cardName;

			void Start(){

			}

			void Update(){
				
			}

		}

## 组件
// 获取对象附加的组件
var animator = GetComponent<Animator>();

## 声明周期函数
> 运行前调用方法(按顺序)
* Awake()    Activity为ture。 在MonoBehavior创建后就立刻调用，只执行一次
* OnEnable() Activity为ture，脚本enable为true。 会在对象被激活后运行，只执行一次
* Start()    会在 Awake() 之后运行，Update()第一次执行前被调用,直到运行完所有 Awake() 方法后，才会调用 LateUpdate 方法

* OnEnter()? 每次进入都会执行一次
* Update()   MonoBehaviour启用时，对象被激活后运行。 每一帧运行
* LateUpdate() 会在 Update() 之后运行，直到运行完所有 Update() 方法后，才会调用 LateUpdate 方法

![QQ截图20190604211833.png](https://img-blog.csdn.net/20150819133318605?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center)
## 协程

## 创建与销毁

> 从预设体创建对象
	public GameObject myPrefab;
	void Start(){
		var newObject = (GameObject)Instantiate(myPrefab);
		newObject.transform.position = this.transform.position;
	}

> 从头创建对象  
	var newObject = new GameObject("My new GameObject");
	var renderer = newObject.AddComponent<SpriteRenderer>();
	renderer.sprite = myAwesomeSprite;

> 销毁
	Destory(this.gamObject);

## 实例化
	Destroy(this.gameObject);

## 特性
### RequireComponent

	[RequireComponent]
	class ClassThatRequiresAnAnimator:MonoBehaviour{
		// 此类要求 GameObject 上关联一个 Animator
	}

### Header

	public class Spaceship : Monobehaviour{
		[Header("Spaceship Info")]
		public string name;
		public Color color;
		[Space]
		public int missileCount;
	}

### SerializeField HideInInspector
> 控制是否在 Inspector 中显示(不改变作用域)

	class Monster : MonoBehaviour{
		// 会显示
		public int hitPoints;
		// 不会显示
		private bool isAlive;

		// 会显示
		[SerializeField]
		private int magicPoints;

		// 不会显示
		[HideInInspector]
		public bool isHostileTpPlayer;
	}

### ExcuteInEditMode
> 编辑模式下 Update 代码

	[ExecuteInEditMode]
	class LookAtTarget : MonoBehaviour{
		public Transform target;

		void Update(){
			if(target != null){
				return;
			}

			// 转动以面对目标
			transform.LookAt(target);
		}
	}

### DisallowMultipleComponent
> 不允许多次附加此组件

### Debug

	Debug.Log("Message! 1 + 1 = {0}", 1+1);

###
* 通过 Tag 来检测碰撞  

		private void OnTriggerEnter(Collider other)
		{
			if(other.CompareTag("Player"))
			{
				Destory(gameObject);
			}
		}

# 资源(Asset Workflow)
## 图像
后缀为:BMP,TIF,TGA,JPG,PSD
## 模型
后缀为:**FBX**,max,blend,mb,ma,obj
## 动画
## 声音
## 资源包-标准资产(Standard Assets)
后缀为:unitypackage
## 自带包-(Unity Package Manager's Assets)
https://docs.unity3d.com/2019.1/Documentation/uploads/Main/PackageManagerUI-Main.png

# 游戏对象(GameObjects)
## 概述
* 所有东西都是游戏**对象**(同时没有任何作用)
* 游戏**对象**通过附加**组件**来实现具体的行为
四种不同类型的GameObject：动画角色，灯光，树木和音频源
![1](https://docs.unity3d.com/2019.1/Documentation/uploads/Main/GameObjectsExamples.jpg)
## API  
https://docs.unity3d.com/2019.1/Documentation/ScriptReference/GameObject.html

## 组件的示例(Component)
一个空对象会包含一个默认的组件:**Transform**
* 属性1:位置(Position)
* 属性2:旋转(Rotation)
* 属性3:比例(Scale)  
![QQ截图20190815191031.png](https://i.loli.net/2019/08/15/9of6NmRcgxVCb8L.png)

## 对象的示例
一个灯光对象
* 创建一个**对象**,命名为灯光
* 添加组件:Light  
![QQ截图20190815185822.png](https://i.loli.net/2019/08/15/NgL4xAOe8zFQ5Xv.png)

一个立方体对象
* 创建一个**对象**,命名为立方体
* 添加组件:Cube
* 添加组件:Box Collider
* 添加组件:Mesh Renderer  
![QQ截图20190815185950.png](https://i.loli.net/2019/08/15/8sBvVQLEHkn15pf.png)

## 标签
用于识别游戏对象的类别,可以自行增加标签，每个对象只有一个标签
* 没有标签(Untagged)
* 玩家(Player)
* 敌人(Enemy)
* 建筑(Building)   
![QQ截图20190815193642.png](https://i.loli.net/2019/08/15/rvCc85ksh4VB3oa.png)

## 静态对象(了解即可)
将对象设置为静态来优化图像渲染
* 场景光(Lightmapping)  
https://docs.unity3d.com/2019.1/Documentation/Manual/StaticObjects.html

# 预设体(Prefabs)
打包好的游戏对象，有利于下列操作
* 重复利用对象，如环境中的大量树木，NPC，发射出的子弹等
* 通过代码初始化对象

## 创建一个预设体
将一个游戏对象拖放到Project窗口(原本的游戏对象会变成蓝色，表示已经成为一个预设体)  
![QQ截图20190815201041.png](https://i.loli.net/2019/08/15/u36OWfGzrvE9kAY.png)

## 编辑一个预设体
在Project窗口选中一个预设体，然后再Inspector选择按钮OpenPrefab/**或者双击预设体**  
> 所有操作会自动进行保存

## 实例的重载
当需要特殊的预设体实例，可以直接再实例上改动，被改动的组件或属性会显示蓝色  
![QQ截图20190815202540.png](https://i.loli.net/2019/08/15/2btKDdsJPnM5oFR.png)

同时，也能在Inspector中体现实例不同与预设体的地方(改动的地方)  
* 恢复(Revert All)-点击此按钮，所有改动的地方会被**撤销,会还原预设体**
* 应用(Apply All)-点击此按钮，所有改动的地方会被**写入到预设体**
> 右键改动的地方，也可以进行此操作
![QQ截图20190815202806.png](https://i.loli.net/2019/08/15/uwDUH1qnycNvZ5Y.png)

## 预设体嵌套
将一个预设体从Project窗口中拖动到Hierarchy窗口的预设体上，使其成为子预设体  
![QQ截图20190815203655.png](https://i.loli.net/2019/08/15/j4IOidHtSrozyVB.png)

## 预设体的变体
* Project窗口右键-Create-Prefab Varient  
![QQ截图20190815204730.png](https://i.loli.net/2019/08/15/touabzfN5SKcPhd.png)
> 变化的数据可以保存到自身，更加可以保存到基础的预设体  
![QQ截图20190815204916.png](https://i.loli.net/2019/08/15/knjDpO7ch4JHWZ6.png)

## 解包，覆盖级别
* 在Hierarchy窗口右键-选择UnpackPrefab
* 覆盖到预设体/覆盖到实例

## 运行时实例化预设体
1. 创建脚本:InstantiationExample.cs

	using UnityEngine;
	public class InstantiationExample : MonoBehaviour 
	{
		// Reference to the Prefab. Drag a Prefab into this field in the Inspector.
		public GameObject myPrefab;

		// This script will simply instantiate the Prefab when the game starts.
		void Start()
		{
			// Instantiate at position (0, 0, 0) and zero rotation.
			Instantiate(myPrefab, new Vector3(0, 0, 0), Quaternion.identity);
		}
	}

2. 创建空对象
3. 将脚本附加到空对象
4. 将Prefab附加到公共变量:My Prefab
5. 运行即可观察到Prefab实例对象被成功创建

# 2019年8月23日  
## 名词解释  

### fbx模型
![PNG-00-模型概览1.png](https://i.loli.net/2019/08/23/qmQcznTBsZiA4dh.png)  
![PNG-01-fbx模型.png](https://i.loli.net/2019/08/23/gbJem8QrzlAFcu4.png)  
fbx:源自 FilmBoX 软件，支持动画的3D模型格式(注意，如果在fbx里面改变材质的话，会导致材质球的材质也改变(实际上就是改变材质球的材质)    
	* Mesh:网格，就是模型的骨架，通常由很多个三角形组成，通常已经整合在fbx文件里面  
	![PNG-02-网格Mesh.png](https://i.loli.net/2019/08/23/29j81CNRO3iSZHM.png)
	* Meterials:材质(又称材质球),后缀为.mat的一个独立文件，需要指定一个图片如png,psd等作为纹理(如果是别人做好的模型，一般是绑定mat材质的，如果要更改，就要更改mat材质所指向的png/psd纹理)    
	![PNG-03-材质球mat与材质psd.png](https://i.loli.net/2019/08/23/uVD8PMHLSEvy74B.png)
		* psd:RT  
		* png:RT 
		 
### animations:动画 

fbm:不是文件格式后缀，通常是文件夹名字，表示此文件夹存放的是fbx模型的mat材质文件
prefab:
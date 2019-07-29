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
* Awake()    会在对象被实例化后执行，只执行一次
* Start()    会在 Awake() 之后运行，直到运行完所有 Awake() 方法后，才会调用 LateUpdate 方法

* Update()   会在对象被激活后运行，每一帧
* LateUpdate() 会在 Update() 之后运行，直到运行完所有 Update() 方法后，才会调用 LateUpdate 方法

* OnEnable() 会在对象被激活后运行，只执行一次

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



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
* 通过 Tag 来检测碰撞

    private void OnTriggerEnter(Collider other)
    {
        if(other.CompareTag("Player"))
        {
            Destory(gameObject);
        }
    }

* 在 Inspector 中绘制标签以及空行 **Header** & **Space**

	public class Spaceship : MonoBehaviour{
	   [Header("Spaceship Info"")]
	   public string name;
	   public Color color;
	   [Space]
	   public int missileCount;
	}

* 在 Inspector 中显示私有变量 **SerializeField**

	[SerializeField]
	private int magicPoints;

* 记录变量到控制台

    Debug.Log("Message! 1 + 1 = {0}", 1+1);

The Explorer:3D Game Kit(探险者:3D游戏开发)

# Quick Start
* 创建新场景 Kit Tools > Create New Scene
    * 会预设部分对象
* 功能：对象简单移动
    * 使用方法：使用脚本 **Simple Translator**
        * 属性：**Start/End** 的两个点定义移动位置
        * 属性：**Loop Type** 定义循环模式
    * 脚本位置：Packages > Interactive > Actions > SimpleTranslator 
    * 功能图例：
        * ![QQ截图20191216154703.png](https://connect-cdn-prd-cn.unitychina.cn/20190130/9c7a292d-a059-4b7b-b660-a4ea9cf66e26_3d_game_kit_quick_start_part_1_12.png)  

* 功能：使用命令开启门
    * 使用方法：放置对象压力板 **PressurePad** 与门 **DoorSmall**
        * 使用脚本：**Send On Trigger Enter**
        * 属性：**Interaction Type** 定义作用的类型如开启/关闭
        * 属性：**Interactive Object** 定义作用的对象(DoorSmall)
        * 属性：**Layers** 触发层
    * 脚本位置：Packages > Interactive > Runtime > Senders > SendOnTriggerEnter  
    * 功能图例：
        * ![QQ截图20191216154703.png](https://connect-cdn-prd-cn.unitychina.cn/20190130/f5a07343-a535-40f2-afbf-c9421686c907_3d_game_kit_quick_start_part_1_19.png)  
    
* 功能：怪物
    * 使用方法：直接放置Chomper 基础功能：敌人扫描，扫描半径，扫描角度(若未增加追踪功能，则只会原地移动)
        * 使用脚本：**Chomper Behavior**
    * 功能图例：
        * ![QQ截图20191216154703.png](https://connect-cdn-prd-cn.unitychina.cn/20190130/42e573fc-be08-4b7a-9342-e4ae1264512c_3d_game_kit_quick_start_part_1_26.png)  
    
    * 增加：**Plane** 追踪功能：设定代理类型(怪物)，包括层
        * 增加组件：**NavMeshSurface**，配置参数后，通过 Bake 生成追踪层
        * 功能图例：
            * ![GIF 2019-12-17 9-28-15.gif](https://i.loli.net/2019/12/17/XQjF7EYKdn2hrVM.gif)

* 功能：可被破坏物品 **DestructibleBox**
    * 子对象：DestructibleBox & Audio
        * 功能图例：
            * ![QQ截图20191217160953.png](https://i.loli.net/2019/12/17/emtzpVj4Gb8qcrF.png)  
        * 脚本：Damageable 及其流程
            * 反激活 DestructibleBox ，激活并复位 DestructibleBoxBreak
            * 激活 DestructibleBoxCollider
            * 调用 Audio -> RandomAudioPlayer.PlayRandomClip
        * 脚本：Dissolve
            * 遍历对象的Renderer，使用基础ParticleSystem播放动画
                * m_Renderer = GetComponentsInChildren<Renderer>();
                * m_ParticleSystem = GetComponentInChildren<ParticleSystem>();
            * API:https://docs.unity3d.com/2019.1/Documentation/ScriptReference/ParticleSystem.html
    * 增加功能：关于可破坏物件与怪物的碰撞
        * 增加脚本:Contact Damager并指定伤害与层，增加组件:Box Collider
        * 功能图例：
            * ![QQ截图20191217170203.png](https://i.loli.net/2019/12/17/wOqYdHagjV1QUWn.png)
    
* 功能：地形
    * 地形烘培:在更新了物品后，需要重新烘培  Plane->NavMesh->Bake

* 功能：**植被编辑器-WorldBuilding**
    * Packages->WorldBuilding->Runtime->InstancePainter
    * 通过此插件和预制体能快速创作地形植被
    * 基本操作
        * 单击=绘制
        * Ctrl+单击=删除
        * Alt+滚轮=调整画笔大小
        * **空格=随机位置与旋转**

* 功能：传送门
    * 脚本位置：Prefabs->Environment->Structures-GateWayHugeTeleporter
    * 碰撞：对子对象TeleportPlane增加组件：Box Collider，并勾选 Is Trigger
    * 碰撞：对子对象TeleportPlane增加脚本：Teleporter
        * Layer 改为 Player
        * Checkpoints子对象Checkpoint,赋值:GateWayHugeTeleporter子对象TeleportPlane的Teleporter组件的Destination Transform
            * ![GIF 2019-12-17 19-19-42.gif](https://i.loli.net/2019/12/17/t7YA25L6ZxoqCaJ.gif)
        * Ellen子对象RespawnParticles,赋值:GateWayHugeTeleporter子对象TeleportPlane的Teleporter组件的Enter Effect和Exit Effect
            * ![GIF 2019-12-17 19-25-19.gif](https://i.loli.net/2019/12/17/bOfvkh74uQNtgc2.gif)

# 3D Game Kit Walkthrough


# 3D Game Kit Reference Guide


# Solution
* 破坏
    1. 替换可分拆对象(由分拆对象模拟的副本)并调用融化脚本 Dissolve (要求分拆对象要全模型上色)

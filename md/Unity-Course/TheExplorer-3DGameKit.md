The Explorer:3D Game Kit(探险者:3D游戏开发)

# Quick Start
* 创建新场景 Kit Tools > Create New Scene
* 功能：对象在游戏内简单移动：使用脚本 **Simple Translator**
    * 通过 Start End 的两个点定义移动位置，Loop Type 定义循环模式
    * 脚本位置：Packages > Interactive > Actions > SimpleTranslator 
    * ![QQ截图20191216154703.png](https://connect-cdn-prd-cn.unitychina.cn/20190130/9c7a292d-a059-4b7b-b660-a4ea9cf66e26_3d_game_kit_quick_start_part_1_12.png)  

* 功能：使用命令开启门
    * 放置压力板(PressurePad)与门(DoorSmall)
    * 脚本位置：Packages > Interactive > Runtime > Senders > SendOnTriggerEnter  
    * ![QQ截图20191216154703.png](https://connect-cdn-prd-cn.unitychina.cn/20190130/f5a07343-a535-40f2-afbf-c9421686c907_3d_game_kit_quick_start_part_1_19.png)  
    
* 功能：怪物
    * Chomper 基础功能：敌人扫描，扫描半径，扫描角度(当前只会原地移动)
        * ![QQ截图20191216154703.png](https://connect-cdn-prd-cn.unitychina.cn/20190130/42e573fc-be08-4b7a-9342-e4ae1264512c_3d_game_kit_quick_start_part_1_26.png)  
    
    * 怪物追踪功能：设定代理类型(怪物)，包括层
        * 增加组件：NavMeshSurface
        * ![GIF 2019-12-17 9-28-15.gif](https://i.loli.net/2019/12/17/XQjF7EYKdn2hrVM.gif)


* 功能：可被破坏物品(DestructibleBox)
    * 组件：DestructibleBox & Audio
        * ![QQ截图20191217160953.png](https://i.loli.net/2019/12/17/emtzpVj4Gb8qcrF.png)  
    * 脚本：Damageable
        * 反激活 DestructibleBox，激活并复位 DestructibleBoxBreak
        * 激活 DestructibleBoxCollider
        * 调用 Audio -> RandomAudioPlayer.PlayRandomClip
    * 脚本：Dissolve
        * 遍历对象的Renderer，使用基础ParticleSystem播放动画
            * m_Renderer = GetComponentsInChildren<Renderer>();
            * m_ParticleSystem = GetComponentInChildren<ParticleSystem>();
        * API:https://docs.unity3d.com/2019.1/Documentation/ScriptReference/ParticleSystem.html

# 3D Game Kit Walkthrough


# 3D Game Kit Reference Guide


# Solution
* 破坏
    1. 替换可分拆对象(由分拆对象模拟的副本)并调用融化脚本 Dissolve (要求分拆对象要全模型上色)
    2. 
    3. 

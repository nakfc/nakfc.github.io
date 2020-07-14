# 1.Example Scenes
## Passive AI-被动
> Demonstrates(示范) an AI that roams(漫游) around passively(被动/消极)
A Passive Ai will only react(作出反应) to its target if it is damaged.
Its actions are based on its Confidence(信心) Level.
If an AI is set to Coward(懦夫),it will flee(逃跑),If an AI is set to Brave it will fight until its health is low.If an AI is set to Foolhardy(鲁莽),it will continue to fight until death.
## Terrirotial AI-领域
> Demonstrates an AI that is territorial(自有领域 英 /ˌterəˈtɔːriəl/ ).A Cautious(谨慎的) AI will watch a target before it attacks.It will play a warning animation before it is about to attack.If the target does not leave its radius soon,the AI will initialize an attack.If the target exits the AI's radius,it will resume wander(徘徊).
## Compainion AI-同伴
> Demonstrates an AI that is that acts as a companion(同伴 英 /kəmˈpænjən/ ).
Companion Ai will follow around an object with the appropriate(合适的) tag.in this case,the Player tag.The companion AI will fight for the player and resume following the player when it is finished with combat(战斗).
## Aggressive AI-主动
> Demonstrates an Aggressive(侵略性 英 /əˈɡresɪv/) AI that is that acts an hostile towards any target with the appropriate tag.
## Pet AI-装饰宠物
> Demonstrates an AI that is that acts as a non-combat pet.Pet AI cannot attack or be apart of combat.They are purely for cosmetic(装饰) purposes.
## Line of Sight-视线检测
> Demonstrates an AI that uses Line of Sight to detect(察觉) the Player.The angle for this is about 200".
## Combat Text & Health bar
## Setting Up
> An example scene that's intended to be used for follow along with the Setting up your Own AI guide below.
## Fleeing AI
> fleeing from the player.

# 2.Setting Up your Own AI
> Window->Emerald AI->Emerald AI Setup Manager
## 步骤
### 1.添加Emerald AI
1. 打开窗口  
    Windows->Emerald AI->Setup Manager
2. 选择游戏对象  
    选择一个带有动画组件:Animator的游戏对象作为 AI Object
3. 点击 Setup AI  
    点击按钮完成添加(此时已经在场景运行)

### 2.修改AI
1. 为所有动作添加动作片段
2. 添加所有必须战斗参数





# 3.DEMO介绍-Emerald AI System(Script)
## Temperament
![01.png](https://i.loli.net/2020/04/21/ZLF1CozyIXRA82t.png)  
### Behavior
> 定义AI的行为
1. Passive-消极攻击
2. Cautious-谨慎
3. Companion-同伴
4. Aggressive-主动攻击  

### Confidence
> 定义AI的进一步行为:信心
1. Coward-懦夫
2. Brave-勇敢
3. Foolhardy-有勇无谋的
### Wander Type
> 游走类型
1. Dynamic-动态
2. Waypoints-路径点
3. Stationary-静止
4. Destination-目的地
### Combat Style
> 战斗类型,只支持 Companion
1. Offensive-进攻性
2. Defensive-防御性
## AI's Settings
![02.png](https://i.loli.net/2020/04/21/cKwVoXYMNkRbZp5.png)  
### Stats
> 一些基本的AI状态如名字
### Movement
> 移动相关设置。例如运动速度、路线、转弯、等待时间和停车距离
### Combat
> 战斗相关设置。例如
### NavMesh
> AI网格导航相关设置。
### Optimize
> 优化设置
### Events
> AI事件。例如 On Start,On Enabled,
### Items
## Detection & Tags
> 侦测与标记
![03.png](https://i.loli.net/2020/04/21/j8pWQZbF3K5tdav.png)  
### Detection Options
> 控制各种检测相关的选项和设置，如半径距离、目标检测和视野
### Tag & Faction Options
> 设置Tags和Layers用于检测,派系选项允许你控制你的ai视哪些派系为敌人或盟友
#### Tag Options
> Tag选项
#### Faction Options
> 派系选项
#### Head Look Options
> 视线检测
## UI Settings
> 设置用于触发UI的Tag和Layers
![04.png](https://i.loli.net/2020/04/21/BxwHpnfVoN1DLFP.png)  
## Sounds
![05.png](https://i.loli.net/2020/04/21/hSmDxfYEblje3z2.png)  
### General
> 通常声音
### Combat
> 战斗声音
## Waypoint Editor
> 当AI's Wander Type 设置为Waypoints可用，进一步设置相关巡逻路径点

## Animations
![06.png](https://i.loli.net/2020/04/21/UE3gnZArlsW6tdc.png)  
### Idle
> 通常类动画
### Movement
> 移动动画
### Combat
> 战斗动画
### Emotes
> 表情动画

## Docs
![07.png](https://i.loli.net/2020/04/21/Z7Nb4aoFtfTr8cg.png)  

# 总结
0. 若需要简单使用此系统，建议直接使用自带的Prefabs来修改
1. 当AI发出近战攻击动作时，若玩家进行移动即可避免伤害？
2. 只需要使用 Setup Manager 即可简单添加AI组件(会自动添加所有需要的脚本 4+1+动画)


# 资料
![QQ截图20200421122039.png](https://i.loli.net/2020/04/21/fOdE23Cpi9whPsr.png)  
指南:https://github.com/Black-Horizon-Studios/Emerald-AI/wiki
API:https://docs.google.com/document/d/1ns8m7Ol_gaKeYJ3YbaRjDy09xG98UoIXKCaWLGJeg74/edit#
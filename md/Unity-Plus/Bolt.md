# Bolt Kit:First Person  
## 项目简介 
* 结构  
![GIF 2019-12-11 13-03-52.gif](https://i.loli.net/2019/12/11/xsvdt9cZEa3oRD5.gif)  

## Scene:GUI
## Scene:Level01
* 场景概览：  
![GIF 2019-12-11 15-19-27.gif](https://i.loli.net/2019/12/11/ARXgvH9jrahFyUd.gif)  
* Environment-无功能的环境UI集合  
* Sun-Light组件  
* Scene Variables-Bolt常规核心组件，用于保存场景变量  
* **Protal**-传送门，核心游戏元素  
    * ![GIF 2019-12-11 14-01-49.gif](https://i.loli.net/2019/12/11/xWokwLUrbZeD8KX.gif)  
* **Player**
    * ![GIF 2019-12-11 14-10-58.gif](https://i.loli.net/2019/12/11/KDwhUBTrilx9y3J.gif) 
* KillFloor
    * ![GIF 2019-12-11 14-46-17.gif](https://i.loli.net/2019/12/11/c9nefq7iDGJoWgh.gif)  
* GuiLoader
    * ![GIF 2019-12-11 15-08-14.gif](https://i.loli.net/2019/12/11/SgKwfQbCvjkAezt.gif)
* Canvas-
* EventSystem-Bolt事件系统
    * ![GIF 2019-12-11 15-22-58.gif](https://i.loli.net/2019/12/11/pOt8vcn7m1LSgE2.gif)
* GameManager-自定义游戏管理员
    * ![GIF 2019-12-11 15-22-04.gif](https://i.loli.net/2019/12/11/uYv4jIqoftLHNxZ.gif)


## Scene:Level02
## Scene:Level03
## Scene:Level04

# 3D Game Kit
## Player Controller - Ellen
## World Building - Instance Painter
## Pressure Pad
## Objects - Weapons
### Melee Weapon
### Range Weapon
## Objects - Projectile
## Enemy Controller - Parameters
## Enemy Controller - Navmash Agent Priority
## Enemy Controller - External Force
## Damage System - Damageable
## Damage System - Checkpoints
## Damage System - Damage Zone
## Damage System - Death Volume
## Damage System - Contact Damager
## Damage System - Scenelinked SMB
## Target Scanner - Parameters
## Gameplay Componentes - Command System
## Gameplay Componentes - Send Game Command
## Gameplay Componentes - Game Command Receiver
## Gameplay Componentes - Game Command Handler
## Gameplay Componentes - Send Game Command Sub-types
### Send On Became Visible
### Send On Collision Enter
### Send On Collision Exit
### Send On Collision Stay
### Send On Trigger Enter
### Send On Trigger Exit
### Send On Trigger Stay
## Gameplay Componentes - Game Command Handler Sub-types
### Moving Platform
### Interact On Trigger Health Crates
### Trigger Unity Event
### Toggle Game Object Active
### Switch Material
### Start Playable Director
### Simple Rotator
### Simple Translator
### Set GameObject Active
### Set Animator Trigger
### Respawn Player
### Play Sound
### Play Animation
### Particle System Emit
### Gameplay Counter
### Simple FX Synth

# Peek And Bolt
## Peek
* Inspect Components in scene without Inspector
* Full screen with tabs
* Pin Components in scene 
* Quickly inspect components referenced

* Quick - Create game objects in scene (Ctrl + Shift + Click)
* Quick - Groups game objects (Ctrl + G)
* Quick - Find game objects in scene (Ctrl + F)
* Quick - Popup hierarchies with game objects selected(Space)
* Quick - Pins game objects inspector with component selected(Space)

## Bolt
### Windows
* Graph
* Graph Inspector
* Valiables

### 
Flow Mechine
State Mechine

# Playmaker
## 基础概念  
* Global Transition （即过渡到某个状态）  
    * 任意时候可被触发的**触发器**  
    * 通常在外部调用

* State（即当前在这个状态并且做一些事情）  
    * 核心-处理各种Actions，有需要时，通过Add Transition 发送 Events 到其他State（不小心增加的Transition可以 Delete Transition）  

* Transition Event（State处理完成后再跳转到某个State）  
    * 一个或多个Event，用于跳转到其他State  



Unity-中级教程-PlayMaker生命系统《Udemy - Create a Fun Life Simulator Game using playMaker and Unity》
## 视频简要
5【】Sending Events to State Machines and Modifying Variables
6【00:00-07:40】
6【08:00-End】Creating State Machines for Game Items（创建Item自己的FSM替换GM的FSM，引出【全局变量】以及【自身局部增量】）
7【00:00-04:25】建立单个具有自身FSM的Beg‘s Item后(引出Prefab来批量生成其他 Item)
7【00:00-04:25】使用Prefabs，(引出Health可以为负数的bug)
--新建项目复习1-7
8【】
9【】
10【】
11【】
12【】
13【】
14【】
15【】
16【】
17【】
18【】
19【】
20【】
 
## 按键与UI的数据同步（视频章节1-5）
1.Playmaker定义Events如:Click Button
2.Playmaker定义State如:Process Click Button
3.State链接Events
    右键State->Add Global Transition->Click Button
4.定义State具体执行操作如数学运算:Int Add
    State右下角->Action Browser->Int Add
5.定义一个按键按下的自定义事件如:Click Button
    GameManager->PlayMakerFSM.SendEvent->Click Button
6.当变量改动使之体现到UI
    * 右键State-Add Global Transition->FINISHED
    * 链接 FINISHED 到 Update UI

## 
## 
## 
## 



# 还需要了解的
## NGUI
https://assetstore.unity.com/packages/tools/gui/ngui-next-gen-ui-2413

## 
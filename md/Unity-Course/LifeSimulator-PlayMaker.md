Unity-中级教程-PlayMaker生命系统
《Udemy - Create a Fun Life Simulator Game using playMaker and Unity》

## 视频简要
5【】Sending Events to State Machines and Modifying Variables  
6【00:00-07:40】  
6【08:00-End】Creating State Machines for Game Items（创建Item自己的FSM替换GM的FSM，引出【全局变量】以及【自身局部增量】）  
7【00:00-04:25】建立单个具有自身FSM的Beg‘s Item后(引出Prefab来批量生成其他 Item)  
7【00:00-04:25】使用Prefabs，(引出Health可以为负数的bug)  
--新建项目复习1-7  
8【04:00开始】修复不合理的生命值(大于和小于)以及食物值（大于和小于）（引出当达到某些情况下需要指引如：死亡/胜利）  
9【03：00】在按钮FSM中发送全局Event，在GameManager中设置GlobalTransition接受此全局Event（引出死亡结果的额外UI）  
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
    
![GIF 2019-11-6 19-23-21.gif](https://i.loli.net/2019/11/06/yXrIWckAGwHtv3P.gif)  

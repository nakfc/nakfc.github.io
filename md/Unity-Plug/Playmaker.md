# Playmaker
Unity-中级教程-PlayMaker生命系统《Udemy - Create a Fun Life Simulator Game using playMaker and Unity》

## 简介
Global Transition-(深黑色背景白色字体)指向State,用于触发State,可右键State添加(添加后会显示在Events,若需要可以勾选全局)  
State-(灰色背景白色字体)被箭头指向,会在内部执行若干Action  
Transition Event-(白色背景黑色字体)由一个State转换向其他State  

![QQ截图20191017211748.png](https://i.loli.net/2019/10/17/4cdpe3yrjbT81iN.png)  
![QQ截图20191017211826.png](https://i.loli.net/2019/10/17/DuQZoHS3in9gEvY.png)  
![QQ截图20191017211935.png](https://i.loli.net/2019/10/17/k2ZnH5JszfCbKgp.png)  

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
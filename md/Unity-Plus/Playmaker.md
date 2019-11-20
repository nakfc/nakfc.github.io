
## 一 基础概念  
* Global Transition （深黑色背景白色字体，即过渡到某个状态）   
    * 说明：任意时候可被触发的**触发器** ，通常在外部调用  

* State（灰色背景白色字体，即当前在这个状态并且做一些事情）  
    * 说明:核心-处理各种Actions，有需要时，通过Add Transition 发送 Events 到其他State（不小心增加的Transition可以 Delete Transition）  

* Transition Event（白色背景黑色字体，State处理完成后再跳转到某个State）   
    * 说明：一个或多个Event，用于跳转到其他State  

* 快速创建action   
    * 操作：在FSM中选定一个State(并且打开State选项卡)，然后在Hierarchy中将任意对象拉取到State，然后放开  
    * 说明：会弹出与该对象关联组件的相关方法  
    ![GIF 2019-11-20 16-25-17.gif](https://i.loli.net/2019/11/20/67eQ1Oz4NAbhWIH.gif)  

* 调试 将变量以及事件显示在Inspector->Controls中，可以在调试中测试触发事件  
    * 操作：
    * 说明：
    ![GIF 2019-11-20 16-04-15.gif](https://i.loli.net/2019/11/20/qXM2Ybj1twJS46z.gif)  

## 二 视频内容摘要  
2【All】Creating the unity project and installing playmaker
3【All】创建基本UI如:生命值，食物值，睡眠按钮，食面包按钮（下章节预告：进行更直接的处理和操作）
4【】通过创建一个GM并附加PlayMakerFSM组件来操作其他元素，
5【】Sending Events to State Machines and Modifying Variables 
4【】
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
21【】   

##  三 归纳整理 按键与UI的数据同步（视频章节1-5）
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

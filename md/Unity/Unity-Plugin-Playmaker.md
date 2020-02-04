# Playmaker-基础
# Playmaker-教程
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

## 二 视频内容摘要(Udemy - Create a Fun Life Simulator Game using playMaker and Unity)
### 2 创建 Unity 项目并安装 Playmaker  
### 3 创建基本用户界面  
* 创建基本UI如:生命值，食物值，睡眠按钮，食面包按钮（下章节预告：进行更直接的处理和操作）  
### 4 第一个Playmaker FSM
* **创建FSM**，通过创建一个 GM 并附加 PlayMakerFSM 组件来操作其他元素  
* **增加变量**，为FSM增加变量  
* **监视变量**，为变量勾选 Inspector 使之在组件 Inspector 中显示  
### 5 发送事件消息到FSM并修改变量   
* **定义状态**，在State处定义一个新的状态(例如:)，在 Events 处新增一个事件(例如:Click Button)   
* **链接事件**，选择 GlobalTranstion，然后选择刚才新增的事件(此事件供外部调用触发)   
* **完成事件**，选择 Add Transtion，然后选择 FINISHED 事件(特殊事件，表示当前状态已经完成)   
* **过度状态**，选择 FINISHED，然后链接到其他状态(例如过渡到更新UI的状态)    
### 6 改进设计，创建其他状态机
* **更多的按钮**，在GM的FSM中新建3个状态，分别用事件来触发,它们都指向更新UI的状态
* **改进设计**，新建一个按钮及其FSM，然后尝试更新数据（暂时不更新UI）
### 7 创建Prefabs增强复用性
* **删减状态**，移除GM的FSM中其他状态，单独新增一个状态供全局触发(01：49)  
* **Prefabs创建使用**，将新建的按钮制造成Prefabs，然后按需创建副本
### 8&9 限制最值，全局事件通知
* **最值对比状态**，创建最大值和最小值的对比**状态**(Check Health & Check Food)
* **条件全局通知**，在各个状态中，若满足情况，则进行全局事件通知
### 10 死亡面板以及重置游戏   
* **创建Panel**，右键Canvas->UI->Panel，创建一个与当前Canvas相同大小的Panel，以及增加UI->Text
* **应用Panel**，打开GM的Playmaker的State Player Died的State，拖动Panel到GM的State，选择
* **重开游戏按钮**，更改逻辑，设置全局事件:Global Event RestartGame，设置初始化状态:State GameSetup
### 11 UI-为血量和食物增加可视滑块
* **Slider**，增加Slider组件，移除滑块子组件
* **绑定数据**，在开始状态增加**UI Slider Set Min Max**,在更新状态增加**UI Slider Set Value**  
### 12 数据-创建数组存储数据
* **增加数组**，在Prefabs中增加**Array**类型局部变量:**Requirements**,数组类型为**Game Object**。
* **遍历数组**，增加检查状态，通过**Action:Array Get Next**,遍历数组，遍历后通过FINISHED事件退出状态
* **元素检查**，增加状态Check Requirement，通过**Action:Get Fsm String**，获取元素信息并Debug输出

### 13&14 数据-检查是否符合购买条件 
* **条件判断**，需要列表上所有条件符合才能开始处理，否则进入**事件:Cant Process Item**，并由GM提示所有需要的条件

### 15 

### 16 
* 使用FsmTemplate
### 17 
### 18 
### 19 
### 20 
### 21 

##  三 归纳整理 按键与UI的数据同步（视频章节1-5）
1.Playmaker定义Events如:Click Button  
2.Playmaker定义State如:Process Click Button  
3.State链接Events  
    右键State->Add Global Transition->Click Button  
4.定义State具体执行操作如数学运算:Int Add  
    State右下角->Action Browser->Int Add  
5.定义一个按键按下的自定义事件如:Click Button  
    GameManager->PlayMakerFSM.SendEvent->Click Button  
6.转换到含更新UI功能的State，使当变量改动时体现到UI  
    * 右键State-Add Global Transition->FINISHED  
    * 链接 FINISHED 到 Update UI  

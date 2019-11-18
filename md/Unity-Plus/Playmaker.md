
## 基础概念  
* Global Transition （即过渡到某个状态）  
    * 任意时候可被触发的**触发器**  
    * 通常在外部调用

* State（即当前在这个状态并且做一些事情）  
    * 核心-处理各种Actions，有需要时，通过Add Transition 发送 Events 到其他State（不小心增加的Transition可以 Delete Transition）  

* Transition Event（State处理完成后再跳转到某个State）  
    * 一个或多个Event，用于跳转到其他State 

Global Transition-(深黑色背景白色字体)指向State,用于触发State,可右键State添加(添加后会显示在Events,若需要可以勾选全局)  
State-(灰色背景白色字体)被箭头指向,会在内部执行若干Action  
Transition Event-(白色背景黑色字体)由一个State转换向其他State  

![QQ截图20191017211748.png](https://i.loli.net/2019/10/17/4cdpe3yrjbT81iN.png)  
![QQ截图20191017211826.png](https://i.loli.net/2019/10/17/DuQZoHS3in9gEvY.png)  
![QQ截图20191017211935.png](https://i.loli.net/2019/10/17/k2ZnH5JszfCbKgp.png)  


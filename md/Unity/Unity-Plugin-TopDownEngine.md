# 插件分析
## 结构
![](https://topdown-engine-docs.moremountains.com/images/contents-1.png)  
* Common
* 



# 项目分析
## 项目1.Explodudes
> TopDown炸弹人

### BackgroundMusic.cs
> 背景音乐类，通过调用TD引擎来调用Unity的核心函数 **AudioSource.Play()** 
1. 提供一个编辑器菜单，点击后，会为当前对象新增脚本组件，然后再指定背景音乐
2. 如果同一对象多次添加此组件，只会播放第一个脚本的声音  
3. 代码调用如下，实际上调用了其 MoreMountains.TopDownEngine.SoundManager 类的方法来进行音乐播放
        SoundManager.Instance.PlayBackgroundMusic(_source);
4. 最后通过背景音乐检测后，进行音乐播放(当中涉及一些与配置的交互)

        protected AudioSource _backgroundMusic;

        /// <summary>
        /// Plays a background music.
        /// Only one background music can be active at a time.
        /// </summary>
        /// <param name="Clip">Your audio clip.</param>
        public virtual void PlayBackgroundMusic(AudioSource Music, bool shouldBool = true)
        {
            // if the music's been turned off, we do nothing and exit
            if (!Settings.MusicOn)
                return;
            // if we already had a background music playing, we stop it
            if (_backgroundMusic != null)
                _backgroundMusic.Stop();
            // we set the background music clip
            _backgroundMusic = Music;
            // we set the music's volume
            _backgroundMusic.volume = MusicVolume;
            // we set the loop setting to true, the music will loop forever
            _backgroundMusic.loop = shouldBool;
            // we start playing the background music
            _backgroundMusic.Play();
        }


# 从头开始
## 1.角色的构建
> 最好从现有Demo中开始
https://topdown-engine-docs.moremountains.com/how-to-create-character.html

## 2.角色自身组件属性
![](https://topdown-engine-docs.moremountains.com/images/howtocharacter-2.png)

## 3.添加角色到场景
> 根据 Level Manager，可以预设对象或者运行时生成
1. 
![](https://topdown-engine-docs.moremountains.com/images/adding-to-scene-1.png)  
2. 
![](https://topdown-engine-docs.moremountains.com/images/adding-to-scene-2.png)

## 4.为角色添加新的能力
## 5. 
## 6.
## 7.
## 8.

# 管理员
> 用于管理各种游戏内容，需要给定空对象
## 1. Game Manager
## 2. Level Manager

* 提供两种角色生成方式
    * 运行时(游戏运行才生成角色)
    * 预设(预先在场景中放入角色)
* 通过 MMTweenType FadeCurve 来创建淡入淡出特效
* 通过属性:LevelBounds来约束相机边界

## 3. Input Manager
## 4. Sound Manager
## 5. Loading Scene Manager
## 如何扩展管理员
> todo:继承管理员后，如果复写方法，那么原来的方法会失效？如何保证原本的管理员的全部功能有效而安全地新增功能？

> 例子:扩展 Game Manager

        using UnityEngine;
        using System.Collections;
        using MoreMountains.Tools;
        using System.Collections.Generic;


        namespace MoreMountains.TopDownEngine
        {
            public class NewGameManager : GameManager
            {
                protected override void Start()
                {
                    base.Start();
                    MMDebug.DebugLogTime("new game manager");
                }

                public override void Pause()
                {
                    base.Pause();
                    MMDebug.DebugLogTime("new game manager pause");
                }

                public override void AddPoints(int pointsToAdd)
                {
                    base.AddPoints(pointsToAdd);
                    MMDebug.DebugLogTime("new game manager add points");
                }
            }
        }

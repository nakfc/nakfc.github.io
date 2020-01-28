# Unity-NewGUI
## 1.Transform [doc:Transform](https://docs.unity3d.com/2019.1/Documentation/Manual/class-Transform.html)
> The Transform **component** determines the Position, Rotation, and Scale of each object in the scene
. Every GameObject
has a Transform.

![](https://docs.unity3d.com/2019.1/Documentation/uploads/Main/TransformExample1.png)

## 2.Mesh Filter [doc:Mesh Filter](https://docs.unity3d.com/2019.1/Documentation/Manual/class-MeshFilter.html)
The **Mesh Filter** takes a mesh from your assets and passes it to the Mesh Renderer for rendering on the screen.
> To see the Mesh in your scene,add a **Mesh Renderer** to the GameObject.

![](https://docs.unity3d.com/2019.1/Documentation/uploads/Main/Inspector-MeshFilter.png)

## 3.Mesh Renderer [doc:Mesh Renderer](https://docs.unity3d.com/2019.1/Documentation/Manual/class-MeshRenderer.html)
The **Mesh Renderer** takes the geometry from the **Mesh Filter** and renders it at the position defined by the GameObject's **Transform** component.

![](https://docs.unity3d.com/2019.1/Documentation/uploads/Main/class-MeshRenderer-0.png)

## 4.Canvas [doc:Canvas](https://docs.unity3d.com/2019.1/Documentation/Manual/class-Canvas.html)


![QQ截图20190618194906.png](https://i.loli.net/2019/06/18/5d08cfc8077d560932.png)

## 6.Image

Sliced:切片
Tiled:平铺(拼贴)
Filled:填充

![](https://docs.unity3d.com/2019.1/Documentation/uploads/Main/UI_ImageInspector.png)



## 创建简单Image动画

+ GameObject 增加组件 Image
+ GameObject 增加组件 Animator
+ 选中 GameObject 按键 Ctrl + 6
+ 为 GameObject 创建 Clip(片段) 并保存。(这里Animator会自动绑定新建的Clip)

点击红色按钮进行录制
+ 1.选择时长
+ 2.选择动作 点击GO，点击Image-Fill Amount 改为1(原本为0)



# Unity-OldGUI 
Chapter One - Old Base Widget
## 1.Label(标签)
        
        // Text
        GUI.Label(new Rect(25,15,100,30),"Label");
        // Texture
        public Texture2d myTexture;
        myTexture = new Texture2d(125, 15);
        myTexture = GUI.Label(new Rect(25,15,100,30), myTexture);

## 2.Texture2D(2D纹理)
        public Texture2d myTexture;
        myTexture = new Texture2D(125, 15);
        GUI.DrawTexture(new Rect(325, 15, 100, 15), myTexture);
        GUI.DrawTexture(new Rect(325, 15, 100, 15), myTexture, ScaleMode.ScaleToFit, ture, 0.5f);
        GUI.DrawTexture(new Rect(325, 15, 100, 15), myTexture, new Rect(10, 10, 50, 5));

## 3.Button(按钮)
        GUI.Button(new Rect(25, 40, 120, 30), "ButtonName");
        GUI.RepeatButton(new Rect(25, 40, 120, 30), "RepeatButtonName");
        // TextureButton
        public Texture2D myTexture;
        myTexture = new Texture2D(125, 15);
        GUI.Button(new Rect(25, 40, 120, 30), myTexture);

## 4.TextInput(文本区域)
        string strTextTemp = "";
        string strTextField = "Some text here";
        string srtTextArea = "some more text here";
        string srtPasswordField = "Even more text here";
        strTextTemp = GUI.TextField(new Rect(25, 100, 100, 30), strTextField);
        strTextTemp = GUI.TextArea(new Rect(150, 100, 200, 75), strTextArea);
        strTextTemp = GUI.PasswordField(new Rect(375, 100, 90, 30), strTextPasswordField, "*");

## 5.Box(盒子容器)
        GUI.Box(new Rect(350, 350, 100, 130), "Settings");

## 6.Toggle(开关)
        GUI.Toggle(new Rect(25, 150, 250, 30), false, "Toggle");

## 7.Toolbar(工具栏)
        private int intToolbarIndex;
        private string[] strToolbars;
        // Start()
        intToolbarIndex = 0;
        strToolbars = {"strToolbarFirst", "strToolbarSecond", "strToolbarThird"};
        // OnGUI()
        intToolbarIndex = GUI.Toolbar(new Rect(25, 200, 200 , 30), intToolbarIndex, strToolbars);

## 8.SelectionGrid(选择网格)
        private int intSelectionGrid;
        private string[] strSelections;
        // Start()
        intSelectionGrid = 0;
        strSelections = {"Grid 1", "Grid 2", "Grid 3", "Grid 4"};
        // OnGUI()
        intSelectionGrid = GUI.SelectionGrid(new Rect(250, 200, 200, 60), intSelectionGrid, strSelections, 2);

## 9.Slider(滑动条-自定义最值)
        private float fSlider = 0.5f;
        // OnGUI()
        fSlider = GUI.HorizontalSlider(new Rect(25, 250, 100, 30), fSlider, 0.0f, 10.0f);
        fSlider = GUI.VerticalSlider(new Rect(150, 250, 25, 50), fSlider, 10.0f, 0.0f));

## 10.Scrollbar(滚动条-百分比)
        private float fScroller = 0.5f;
        // OnGUI()
        fScroller = GUI.HorizontalScrollbar(new Rect(25, 285, 100, 30), fScroller, 1.0f, 0.0f, 10.0f));
        fScroller = GUI.VerticalScrollbar(new Rect(200, 250, 25, 50), fScoller, 1.0f, 10.0f, 0.0f);

## 11.ScrollView(通常包含Scrollbar)
        private Vector2 posScroll = Vector2.zero;
        private bool bToggleState = false;
        //onGUI()
        posScroll = GUI.BeginScrollView(new Rect(24, 325, 300, 200), posScroll, new Rect(0, 0, 400, 400), ShowHorizontal, ShowVertical);
        for(int i = 0; i < 20; i++)
        {
                addScrollViewListItem(i, "I'm list item number : " + i);
        }
        GUI.EndScrollView();
        // addScrollViewListItem(int i, string strItemName)
        GUI.Label(new Rect(25, 25 + (i * 25), 150, 25), strItemName);
        bToggleState = GUI.Toggle(new Rect(175, 25, + (i * 25), bToggleState, ""));
****
**Common Widget Features**
## 12.Group
        // onGUI()
        GUI.BeginGroup(new Rect(50, 50, 150, 60));
        GUI.Label(new Rect(10, 10, 100, 30), "Label in a Group");
        GUI.EndGroup();
## 13.Name
        string strLoginText = "Would you like to play a game";
        string strLoginName = "ButtonLogin";
        // onGUI()
        GUI.SetNextControlName(strLoginName);
        strLoginText = GUI.TextField(new Rect(10, 10, 200, 20), strLoginText);

## 14.Focus
        GUI.FocusControl("ButtonLogin");
        string strTempName = GUI.GetNameOfFocusControl();

## 15.Tips
        // Before
        GUI.Button(new Rect(80, 130, 65, 20), "Register");
        // After
        GUI.BUtton(new REct(80, 130, 65, 20), new GUIContent("Register", "My Tips"));

## 16.Windows Widget(CallBack Function)
        void DoMyWindows(int windowID)
        {
                GUI.Label(new Rect(25, 15, 100, 30), "Label");
                GUI.DragWindow();
        }
        // Global
        private Rect rectWindow1;
        // onGUI()
        Rect rectWindow1;
        rectWindow1 = GUI.Window(0, rectWindow1, DoMyWindows, "Controls Window");

## 17.GUI Style
> Config With Inspector

        // Global
        public GUIStyle // 书上的写法，错误的？
        public GUIStyle myGUIStyle;
        // OnGUI()
        GUI.Label(new Rect(25, 15, 100, 30), "Label", myGUIStyle);

## 18.GUI Skin
        public GUISkin MySkin;
        // OnGUI()
        GUI.skin = mySkin;
        GUI.Label(new Rect(25, 15, 100, 30), "Label");

## 19.GUI Event
        if(Event.current.isKey && Event.current.keyCode == KeyCode.Return && GUI.GetNameOfFocusedControl() == "PasswordField")
        {
                CheckUserPasswordAndRegister();
        }
## 20.GUI Layout && BeginArea
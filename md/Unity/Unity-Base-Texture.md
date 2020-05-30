## 名词
* AO:AO是指环境光遮蔽（Ambient Occlusion）
* Diffuse:
* Displacement:
* Normal:
* Roughness:
* Rough Ao:
* UV:vertical
> 我们平时在场景中使用的是【XYZ空间坐标】。
【XYZ空间坐标】决定了【物体对象】在场景中的位置。
【UV坐标】则是决定了【贴图】在【物体表面】的位置。
这个U代表的是水平，V代表的就是垂直。

* albedo[ /æl'biːdəʊ/]:反射率
* smoothness[ /ˈsmuːðnəs/]:平滑度
> HDRP中有，但是URP中不需要？
* normal:法线



SRP:Scriptable Render Pipeline-可编程渲染管线

## 疑问
1.是否支持HDRP和URP(LWRP)取决于资源(也就是.mat的设置决定)？

## Render pipelines
> 几种Unity内置的渲染管线
### 1.Bulit-in Render Pipeline
> 内置渲染管线，默认通用渲染管线，自定义选项有限
### 2.URP:Universal Render Pipeline
> 通用渲染管线，跨平台优化图形，属于SRP其一  
> URP取代了原本的LWRP  
> 在Unity Hub中可以直接创建带有URP的模板  
> 2020.05.07 暂不支持自定义后期处理效果 (post-processing effects)  
使用URP需要安装以下的软件包(实际上只需要安装universal)
* com.unity.render-pipelines.core
* com.unity.render-pipelines.shadergraph
* com.unity.render-pipelines.universal  
![QQ截图20200507214043.png](https://i.loli.net/2020/05/07/KNLPuM9BxwpoHG6.png)  
![QQ截图20200507213731.png](https://i.loli.net/2020/05/07/U1An5FuZOehwTps.png)  
### 3.HDRP:High Definition Render Pipeline
> 高清渲染管线，高端平台高保真图形，属于SRP其二  
> 在Unity Hub中可以直接创建带有HDRP的模板
使用HDRP需要安装以下的软件包
* com.unity.render-pipelines.core
* com.unity.render-pipelines.shadergraph
* com.unity.render-pipelines.high-defintion  
![QQ截图20200507214030.png](https://i.loli.net/2020/05/07/u6MZmvTnqQatp5W.png)  
![QQ截图20200507213723.png](https://i.loli.net/2020/05/07/w8QVEcoMjIGynJ3.png)  
### Render Pipeline Asset
> SRP通过Asset文件来存储数据  
> 通过C#脚本来新增菜单项，通过点击菜单项来手动创建Asset  
> SRP的入口方法为 **Render()**  
> 通过Project Settings -> Graphics 来指定Asset资源   
> 网站:https://docs.unity3d.com/2019.3/Documentation/Manual/srp-creating-render-pipeline-asset-and-render-pipeline-instance.html    
  
> 通过脚本新增的菜单
![QQ截图20200507180625.png](https://i.loli.net/2020/05/07/S2Y8elHNa9osg6d.png)  
  
> 设置Unity使用渲染管线
![QQ图片20200507181856.png](https://i.loli.net/2020/05/07/mUyGngqeCvBAZNi.png)  


配置文件

* 【基本】渲染管线资源和其示例  
* ExampleRenderPipelineAsset.cs  
  
		using UnityEngine;
		using UnityEngine.Rendering;

		// The CreateAssetMenu attribute lets you create instances of this class in the Unity Editor.
		[CreateAssetMenu(menuName = "Rendering/ExampleRenderPipelineAsset")]
		public class ExampleRenderPipelineAsset : RenderPipelineAsset
		{
			// Unity calls this method before rendering the first frame.
			// If a setting on the Render Pipeline Asset changes, Unity destroys the current Render Pipeline Instance and calls this method again before rendering the next frame.
			protected override RenderPipeline CreatePipeline()
			{
				// Instantiate the Render Pipeline that this custom SRP uses for rendering.
				return new ExampleRenderPipelineInstance();
			}
		}

* ExampleRenderPipelineInstance.cs

		using UnityEngine;
		using UnityEngine.Rendering;

		public class ExampleRenderPipelineInstance : RenderPipeline
		{
			public ExampleRenderPipelineInstance()
			{
			}

			// Unity calls this method once per frame for each CameraType that is currently rendering.
			protected override void Render(ScriptableRenderContext context, Camera[] cameras)
			{
				// This is where you can write custom rendering code. Customize this method to customize your SRP.
			}
		}

* 【可编辑】渲染管线资源和其示例  
* ConfigurableRenderPipelineAsset.cs  

		using UnityEngine;
		using UnityEngine.Rendering;

		// The CreateAssetMenu attribute lets you create instances of this class in the Unity Editor.
		[CreateAssetMenu(menuName = "Rendering/ConfigurableRenderPipelineAsset")]
		public class ConfigurableRenderPipelineAsset : RenderPipelineAsset
		{
			// This data can be defined in the Inspector for each Render Pipeline Asset
			public Color exampleColor;
			public string exampleString;

			// Unity calls this method before rendering the first frame.
			// If a setting on the Render Pipeline Asset changes, Unity destroys the current Render Pipeline Instance and calls this method again before rendering the next frame.
			protected override RenderPipeline CreatePipeline()
			{
				// Instantiate the Render Pipeline that this custom SRP uses for rendering, and pass a reference to this Render Pipeline Asset.
				// The Render Pipeline Instance can then access the configuration data defined above.
				return new ConfigurableRenderPipelineInstance(this);
			}
		}

* ConfigurableRenderPipelineInstance.cs

		using UnityEngine;
		using UnityEngine.Rendering;

		// 需要使用Asset的文件？

		public class ConfigurableRenderPipelineInstance : RenderPipeline
		{
			// Use this variable to a reference to the Render Pipeline Asset that was passed to the constructor
			private ConfigurableRenderPipelineAsset renderPipelineAsset;

			// The constructor has an instance of the ExampleRenderPipelineAsset class as its parameter.
			public ConfigurableRenderPipelineInstance(ConfigurableRenderPipelineAsset asset)
			{
				renderPipelineAsset = asset;
			}

			// Unity calls this method once per frame for each CameraType that is currently rendering.
			protected override void Render(ScriptableRenderContext context, Camera[] cameras)
			{
				// This is an example of using the data from the Render Pipeline Asset.
				Debug.Log(renderPipelineAsset.exampleString);

				// This is where you can write custom rendering code. Customize this method to customize your SRP.
			}
		}



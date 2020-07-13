# MarkDown语法介绍
## 1.标题
> 井号+空格+内容(# 标题)
## 2.列表
* 无序列表
* 无序列表
> 星号+空格+内容(* 无序列表)

1. 有序列表
2. 有序列表
3. 有序列表
> 数字+空格+内容(1 有序列表)

## 3.重点/斜体/加粗/下划线

`重点` *斜体*、**加粗**、~~删除线~~

> `重点` 用 '`' 包含字体(数字1左边的符号)

> 斜体 用 '*' 包含字体 (*我是斜体*)

> 加粗 用 '**' 包含字体 (**我是加粗字体**)

> 删除线 用 '~~' 包含字体 (Shift+数字1左边的符号 )

## 4.引用
>在文字行的最前方使用符号'>'

## 5.代码
> 选中所有代码，按下Tab，示例如下面这行

    class hello();    

## 6.分割线
***
> 星号+星号+星号(***)

## 7.超链接
[baidu.com](https://www.baidu.com/index.html)
> 方括号：链接名    括号：URL

> 左方括号+内容+右方括号+左括号+链接URL+右括号

## 8.图片
* **纯图片**

> 感叹号    方括号：图片名  括号：图片URL

> 感叹号+左方括号+内容+右方括号+左括号+图片URL+右括号

![QQ截图20190531215209.png](https://i.loli.net/2019/05/31/5cf1319b8f1d120336.png)

* **带链接的图片**

> 方括号：纯图片样式    括号:链接URL

> 左方括号+感叹号+左方括号+内容+右方括号+左括号+图片URL+右括号+右方括号+左括号+链接URL+右括号

[![QQ截图20190531215209.png](https://i.loli.net/2019/05/31/5cf1319b8f1d120336.png)](https://www.baidu.com/index.html)


<details>
<summary><mark><font color=darkred>Java</font></mark></summary>
<table border="1">
<tr>
  <td><b>JVM</b></td>
  <td>Java虚拟机(Java Virtual Machine):虚拟机包括(字节码指令集,寄存器,栈,垃圾回收堆,存储方法域),运行与平台无关的字节码,并解释成具体OS平台上的指令执行</td>
  </tr>
<tr>
  <td><b>JRE</b></td>
  <td>Java运行环境(Java Running Environment)：JRE可以让编译好的类（字节码）运行起来，是让Java运行起来的最小环境。简单来说JRE=JVM+API（不包括与开发有关的API）</td>
</tr>
<tr>
  <td><b>JDK</b></td>
  <td>Java开发套件(Java Development Kit):程序开发者用于编译调试Java程序的开发包,通常包含JRE</td>
</tr>
<tr>
  <td></td>
  <td></td>
</tr>
<tr>
  <td><b>JSP</b></td>
  <td>Java Server Pages:一种支持动态内容开发的网页技术.其中大部分以<%开始并以%>作为结束标志插入Java代码到HTML页面</td>
</tr>
<tr>
  <td><b>Tomcat</b></td>
  <td><b>Web应用服务器</b>: Servlet 容器，实现了对 Servlet 和 JSP 的支持，并提供了作为Web服务器的一些特有功能，如Tomcat管理和控制平台、安全域管理和Tomcat阀等。</td>
</tr>
</table>
</details>


# 代码块支持
https://www.cnblogs.com/qyf404/p/5019631.html

例子

```c-sharp
using System;
namespace Mono.Cecil {

  public sealed class PinnedType : TypeSpecification {

  public override bool IsValueType {
    get { return false; }
    set { throw new InvalidOperationException (); }
  }
  }
}
```

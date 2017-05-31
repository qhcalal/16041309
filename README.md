# 设计开发报告

------

网站主要由四个页面组成，下面附上他们的url

> * 主页    https://qhcalal.github.io/qhc/
> * 详细页（个人简介）https://qhcalal.github.io/qhc/SelfIntroduction.html
> * 列表页（历史消息）https://qhcalal.github.io/qhc/%E5%88%97%E8%A1%A8%E9%A1%B5.html
> * 表单页（调查问卷）https://qhcalal.github.io/qhc/sheet.html

---
##策划思路
1.该网站的主要功能是个人技术博客。在上面，我会陆陆续续的上传一些代码，技术文章，学习前端时踩过的坑并分享解决思路。
2.完善这个网站的过程也是我不断学习的过程。
3.期望页面整洁，能给用户带来良好的交互体验；层次分明，便于检索；希望他们在上面找到自己想找到的东西
4.内容来源：轮播图 http://www.htmleaf.com/jQuery/ 
            图片 http://www.baidu.com/
            图标字体 http://fontello.com/
            页面布局 https://960.gs/
            
---
##技术指标
1.使用了html5，css3。
2.工具。sublime，用于编辑html；markdown，用于编辑readme文档；github网站，用于提交各网页；firebug，调试。
3.浏览器。火狐


------
## 主页（index.html）


主页包含导航栏，轮播图，表格，雪碧图。

1.作用

**个人博客。在上面你可以看到我最新更新的文章，我会在上传一些代码，技术文章等。**

2.样式

```python
<link rel="stylesheet" type="text/css" media="screen" href="960.css">  
<link rel="stylesheet" type="text/css" media="screen" href="mainstyle.css">
<style type="text/css">
            iframe {
                margin: 0 auto;
                display: block;
                padding: 0;
                width: 100%;
                height: 460px;
                background-color: #fff;
                border: none;
}
</style>
```

其中，外联样式"960.css"搭建了html的框架，"mainstyle.css"是我自定义的样式，里面包含了字体，背景，超链接等设置。这两个外联样式在四个页面都有用到。
内联样式设置了轮播图的位置，大小。

3.导航栏

涉及到了绝对定位
```
{
  position:fixed;
  top:0px;
  left:0;
  height: 28px;
}
```
点击关于站长，你可以看到我的个人简介（详细页），点击一张表单，你可以看到一张调查问卷（表单页）。

4.轮播图

轮播图的图片均来自csdn的个人相册，以防被删。
具体的代码在 practise.html，使用了``<iframe>``标签创建包含该轮播图的内联框架
```
<div class="grid_12" id="frame" >
    <iframe src="practice.html" scrolling="no"></iframe>
</div>
```

5.雪碧图
```
<div class=grid_12 id=footer>
	<ul>
		<li class="icon square"><a href="列表页.html">查看历史文章</a></li>
		<li class="icon triangle"><a href="SelfIntroduction.html">关于我</a></li>
		<li class="icon star"><a href="sheet.html">意见与建议</a></li>
		<li class="icon circle">网站证书</li>
	</ul>
</div>
```
其中类名在"mainstyle.css"中有相关设置。
**点击查看历史文章可以看到列表页**


------
##详细页（SelfIntroduction.html）

1.作用
**该页是我个人简介，帮助用户了解站长。**

同样包含了导航栏，使用的标签有``<nav>`` ``<ul>`` ``<li>`` ``<pre>`` ``<table>``  ``<img>``等
在此贴上超链接的css代码
```
a:link   {color: #3399FF;} 
a:hover  {color: #CC0066;}
a:active {color: #888888;}

a{
  font-size: 100%;
  text-decoration: none;
}
```

--------
##列表页(列表.html)

1.作用
**查看历史文章**

只有这个页我加了背景图片,使用内联样式。
```
<style type="text/css">
		section{
  			margin-top:200px;
  			height: 700px;
  			background-color:#F0F0F0;
  			float:right;
		}
      a{
        font-size: 100%;
        text-decoration: none;
        color: #3399FF;
      }
		aside{
  			margin-top:200px;
  			height: 700px;
  			background-color:#F0F0F0;
		}
		section,aside{
			font-size:110%;
  			font-family:"Microsoft YaHei", "微软雅黑", sans-serif;
  			color:#606060;
		}
		body {background-image: url("http://img.my.csdn.net/uploads/201705/13/1494678058_4345.jpg");}
	</style>
```
利用内联样式优先于外联样式的规则，我重新定义了``<a>``元素。

---------


##表单页(sheet.html)

使用的标签有``<form>``、``<input>``、``<textarea>``、``<select>``、``<submit>``等
1.作用 
**他的作用是吸收用户的建议，以此改善优化网站。**

---
##开发过程中的三个技术难点
---
###提交代码到github
    相关背景知识：git软件使用
    遇到的困难:
    鼠标右键菜单下的git bash莫名消失； 
    git克隆出现ssl认证问题 ；
    生成git   page后网页不能打开
**解决方案：**
    **1.手动添加Git bash 到鼠标右键** 
    步骤：
    1、通过在“运行”中输入‘regedit’，打开注册表。
    2、找到[HKEY_CLASSES_ROOT\Directory\Background]。
    3、在[Background]下如果没有[shell],则右键-新建项[shell]。
    4、在[shell]下右键-新建项[open in Git],其值为“Git Bash Here",此为右键菜单显示名称。
    5、在[shell]下右键-新建-字符串值[Icon],双击编辑，其值为“D:\...\Git\mingw64\share\git\git-for-windows.ico”。此为菜单加图标。
    6、在[open in git]下右键-新建-项[command],其值为 "D:\Program Files\Git\git-bash.exe"

**2.证书错误**
执行代码```git config --global http.sslVerify false```即可

**3.网页404错误**
修改主页文件名为 index.html ，并重新提交。


---

###wordpress安装
    相关背景知识：xampp的安装和使用。
    遇到的困难：无法连接数据库，无法上传。
 具体参照我的博文http://blog.csdn.net/qhcalal/article/details/62221023

----
###第三个技术难点(轮播图)
    相关知识背景：jquery，JavaScript
    遇到的困难：
    轮播的顺序有误
    
解决方案：1.重新调整图片顺序
```
<ul class="slider-img-ul">
    <li><img src="http://img.my.csdn.net/uploads/201705/13/1494679365_7093.png"></li>
    <li><img src="http://img.my.csdn.net/uploads/201705/13/1494679596_1905.png"></li>
    <li><img src="http://img.my.csdn.net/uploads/201705/13/1494679089_2358.png"></li>
    <li><img src="http://img.my.csdn.net/uploads/201705/13/1494679365_7093.png"></li>
    <li><img src="http://img.my.csdn.net/uploads/201705/13/1494679596_1905.png"></li>
</ul>
```
三张图片，按照3，1，2，3，1的顺序排列。

2.


----
##开发心得

建立一个网站就像盖一幢大楼，它是一个系统的流程，得按部就班慢慢来。首先做好网页的框架，在后续学习中不断融入新的元素，就这样定好了四个基本页面，然后再把他们通过超链接联系起来，就构成了一个完整的网站。
目前学习的东西是最基础的，也是表层的，实际上web开发涉及到很多。但是依靠这些基础，一步一步搭建自己的网站，还是带给了我产生了很大的成就感。








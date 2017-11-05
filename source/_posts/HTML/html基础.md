---
title: html基础
date: 2017-11-3
description: 
categories:
- HTML基础
- HTML基础
tags:
- HTML基础 
- HTML基础
toc: true 文章目录
author:
comments:
original:
permalink: 
---
# 一、 前端介绍
- ## 1.1 什么是前端？
> 前端就是提供给用户操作的界面。
       前端开发就是创造界面的过程。

- ## 1.2 前端开发方向
> 前端开发工程师：
              → PC Web、 移动 Web、 混合app 
后端开发工程师：
              → Java、PHP、.NET、Node
全栈开发工程师：
              → 前后端都会。

- ## 1.3 前端的“钱”景
  ![](http://upload-images.jianshu.io/upload_images/5006978-44b9874dfcb68950.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- ## 1.4 技术方向
> HTML
              → 用来描述网页结构和内容。相当于描述人的身体结构和五脏六腑

> CSS
              → 用来美化网页。相当于人穿衣服化妆一样。

> JS
       → 用来实现网页动态效果。相当于人有一些有趣的行为一样

- ## 1.5 快捷键
> Ctrl+C:复制                Ctrl+V:粘贴
> Ctrl+X:剪切                Ctrl+S:保存
> Ctrl+A:全选                
> Ctrl+Z:撤销上一个操作   CTRL＋Y：还原上一个操作   
> Alt+tab:切换程序(注意整个操作过程alt常按)
> Win+D(鼠标点击屏幕的右下角)：切换到桌面
> Win+R：快速运行，打开软件，cmd命令行等
>   mspaint:运行画图工具
>   notepad:运行记事本
>   calc：计算器
>   osk：虚拟键盘
> Win+L:锁屏                F5:刷新
> Alt +f4:退出程序

# 2、 认识浏览器
![](http://upload-images.jianshu.io/upload_images/5006978-83f28111388e9766.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

>  什么是浏览器：
              → 就是用来浏览器网页的工具或软件

>  浏览器的种类：
              → IE浏览器、谷歌浏览器、火狐浏览器、苹果浏览器、欧朋浏览器...

>  浏览器内核：
              → 内核（Rendering Engine）：可大概译为“渲染引擎”，不过我们一般习惯将之称为“浏览器内核”。负责对网页语法的解释（如标准通用标记语言下的一个应用HTML、JavaScript）并渲染（显示）网页。
              网页对普通用户来说就是一个可操作的界面，但对于我们开发者或浏览器而言，网页就是代码。

![](http://upload-images.jianshu.io/upload_images/5006978-ba921222cf4d3a5c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 浏览器内核就相当于一个“翻译官”，将我们的所写的代码翻译成一个可视化的界面。
> 内核的分类：
       → Trident：ie , 猎豹安全浏览器,360极速浏览器,百度浏览器...
       → Gecko：Firefox
       → Webkit：Safari
       → Blink：Chrome，Opera
       不同的内核在渲染同一内容的时候会有差别。

# 3、认识服务器
> 什么是服务器？
       服务器，简单理解就是一个配置比较高的，需要一天24小时运行的超级电脑。
       我们将来所开发好的项目或网站都要部署在服务器上，接入互联网，被全世界访问。

# 4、HTML
- ## 4.1 什么是HTML?
> HTML (Hyper Text Markup Language),超文本标记语言
       → 超文本
                    就是比普通的文本要牛！ 就好像超人 与 普通人一样。
       → 标记
                    也被称为“标签”，超文本之所以比普通文本牛，就是因为有特殊的标记。
       → 语言
              沟通方式，和浏览器说话用的语言。

> 所以，超文本标记语言就是通过一些特殊的标记告诉网页中应当显示什么。

> 作用：
              用来描述网页结构和内容。相当于描述人的身体结构和五脏六腑

- ## 4.2 HTML的标准和主流版本
> W3C（World Wide Web Consortium）
              → 万维网联盟，万维网联盟创建于1994年，是Web技术领域最具权威和影响力的国际中立性技术标准机构。
              → 制定了HTML的标准。
              → 提供了工具书（手册）

> HTML主流版本：
       → HTML4.01
       → XHTML1.0
       → HTML 5.0  推荐使用的版本

网页构架
![](http://upload-images.jianshu.io/upload_images/5006978-88391b9765030ccf.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](http://upload-images.jianshu.io/upload_images/5006978-bfa83fe2dcb5e0d6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 注意：
> → 将来在使用DOCTYPE的时候建议使用html5的类型。每个页面都要设置一个doctype，如果不设置，浏览器会默认开启quirks mode（怪异模式）解析（quirks mode（怪异模式）是浏览器为了兼容很早之前针对旧版本浏览器设计、并未严格遵循 W3C 标准的网页而产生的一种页面渲染模式）
> → 在主体中所看的内容，都要写在body标签中

## 5、开发工具
我常用的开发工具就是如下图标：
微软的 [visual studio code](https://code.visualstudio.com/) 以及 [Webstorm](http://www.jetbrains.com/webstorm/)
![](http://upload-images.jianshu.io/upload_images/5006978-fa788f3782c49da3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

vscode( visual studio code 简称) 是目前打开速度比较快的编辑器，建议使用。插件推荐使用如下：
![](http://upload-images.jianshu.io/upload_images/5006978-2c3bf6e24e4ec1cc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![](http://upload-images.jianshu.io/upload_images/5006978-b800de8aa5b7223d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![](http://upload-images.jianshu.io/upload_images/5006978-58ea5cae6c22a8c6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![](http://upload-images.jianshu.io/upload_images/5006978-9bcf2cc83bbe238a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![](http://upload-images.jianshu.io/upload_images/5006978-f52ac07c451002c8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![](http://upload-images.jianshu.io/upload_images/5006978-4dcc0505ad55ba6b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![](http://upload-images.jianshu.io/upload_images/5006978-4e78842387de1562.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![](http://upload-images.jianshu.io/upload_images/5006978-447c0400f8b01946.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 6、HTML标签
> h标签：
       作用：表示一个标题
       语法：h1到h6分六个等级
       <h1>标题</h1>
       <h2>标题</h2>
              ...
              <h6>标题</h6>
语义（含义）：标题
       特点：独占一行，上下有默认间距。

> p标签：
       作用：表示一个段落。
       语法：
                     <p>段落</p>
       语义：段落
       特点：独占一行，上下有默认间距

> title标签：
       作用：表示网页的名称
       语法：
              <title>网页的名称</title>
       语义：网页名称
       特点：写在head标签里。

> br标签：
       作用：实现换行
       语法：
                     < br >

> hr标签：
       作用：表示一条水平线
       语法：
                     < hr >

> meta标签：
       作用：用作网页配置
       语法：
                     <meta>
       meta标签属性：
                     charset,表示字符集，将来会告诉浏览器在解析网页中的内容时，按照哪种编码解析，具体按照哪种编码由等号后面的值决定。
              如：<meta charset="utf-8">
       特点：写在head标签里且写在最上面。
注意：
              创建好的文件以及文件中的内容会按指定的编码格式转换成二进制（0和1）存放到硬盘里。读取时，也会按照之前保存到硬盘里的编码格式把二进制转换成我们能够看到懂的内容显示。

>   若读取时的编码格式与保存时的编码格式不一致，则会造成内容混乱（乱码）。
>   常用字符集（字库）：
       utf-8:
              国际通用字符集
       gb2312:
              简体中文字符集和英文、数字和少量的特殊符号
       gbk:
              简体中文字符集和繁体中文字符、英文、数字和少量的特殊符号
    
       相同点：
              都是字符的编码格式
       区别：
              大小：
                     utf-8>gbk>gb2312
              性能：
                     uft-8<gbk<gb2312

需要了解一下的标签：
![](http://upload-images.jianshu.io/upload_images/5006978-8f176a741c105c65.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

img标签：
![](http://upload-images.jianshu.io/upload_images/5006978-9fc78957af0361a3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 路径：
> 绝对路径：（了解）
       带有盘符的路径。
              如：C:/Users/Bruce/Desktop/01-HTML第一天\02-其他资料\案例\04春夏秋冬/images/chun.jpg
缺点：可移植性差
​       
> 带有网址的路径：
              如：https://img12.360buyimg.com/da/jfs/t3172/29/7532815266/78514/96c6e177/58ba3348N479cafe1.jpg

> 相对路径：（重点）
       图片和html文件在同一目录时，html文件可以直接使用图片

       html文件在图片的上级目录时，html文件需要先找到图片所在的目录，进去再找图片。

       图片在html文件的上级目录时，html文件需要先返回上级目录，再去找图片。
![](http://upload-images.jianshu.io/upload_images/5006978-bd67d42fb481adec.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![](http://upload-images.jianshu.io/upload_images/5006978-c57486a6cc498dae.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![](http://upload-images.jianshu.io/upload_images/5006978-3412f5f4a8219707.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![](http://upload-images.jianshu.io/upload_images/5006978-52b8ee5290f8e040.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![](http://upload-images.jianshu.io/upload_images/5006978-d8ab1cf85c0b0449.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![](http://upload-images.jianshu.io/upload_images/5006978-ccbf159ac0970ef9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

单元格合并：
- 横向合并：
~~~base
colspan:
<td colspan="4">统计：</td>   /横向合并4个单元格
~~~
- 纵向合并：
~~~base
rowspan:
<td rowspan="4">蜀国</td>   /纵向合并4个单元格
~~~

表单元素：
![](http://upload-images.jianshu.io/upload_images/5006978-9e500966a7cae523.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
> 注册页面上能够填写的内容都是我们的表单元素。
> 作用：用来收集用户的信息，将来提交到服务器。

![](http://upload-images.jianshu.io/upload_images/5006978-944ed3042db5b362.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
> 注意点：如果想要多个radio或者checkbox组成一个选择集合，那么必须给每个radio以及checkbox都设置相同name属性。
> 如何给radio,checkbox设置默认值呢？
> 设置另外一个属性：checked=”checked”
    我需要给下拉框设置默认值？
selected="selected"
> 如果下拉按钮想多选，
~~~base
<select size="4" multiple="multiple">      /*size的意思就是框的大小
~~~

# 7、Html中空格的合并现象：
> 特点：无论在页面有同时出现多少个空格，缩进，换行，将来浏览器在解析的时候只会当一个空格显示。
> 结论：html中对空格，缩进，换行不敏感，如果同时出现多个空格缩进或者执行，页面只会把它们当作一个空格来解析。
> 特殊字符对应的转译符：
> ![](http://upload-images.jianshu.io/upload_images/5006978-a274d086f721a078.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 8、SEO与标签的语义化：
> SEO：搜索引擎优化。
> 作用：用来优化网站，使用网站在搜索引擎上的排名先前。
> 百度是如何收录一个网站的信息的呢？
> 百度自己写的一个程序来收录每个网站的信息。
> 标签语义化的应用：每个html标签都有属于自己的语义，有使用标签时候要一定要了解每个标签的语义，合理使用。（在合适的地方使用合适的标签。）
> 语义化的好处：
> 01对搜索引擎的友好（将来网络爬虫进入页面之后可以很方便的得到页面的重要信息。）
> 02提升用户体验
> 03利于代码的可读、维护、提高开发效率.
> Html中大部分的标签都具有语义，所在使用的时候一定要注意。还有一部分标签没有语义，没有语义的标签一般只用来进行布局。

## 9、HTML总结
> html:超文本标记语言。可以表示图片，音频，视频，超连接（a）.
> html的作用：用来页面的内容添加语义，用来确定html页面的结构。
> html：决定页面的结构（给内容添加语义） 骨骼
> css: 决定页面的样式（使用页面更好看）   穿着
> JavaScript:决定页面的行为（使页面动起来） 行为






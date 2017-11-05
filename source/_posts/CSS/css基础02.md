---
title: 02.CSS基础02
tags: CSS
categories: CSS
date: 2017-11-04
---
# 1、CSS文本样式属性
> text-align：
       作用：规定文本的水平对齐方式。
       语法：
              text-align:left;    向左对齐  默认的
       text-align:right;   向右对齐
              text-align:center;  中心对齐
       注意：
             → 对齐时，要以选择器所代表的元素的宽度为参考。
             → 图片、表单元素、行级元素都可以看成文本。


> text-indent：
> 作用：文本首行缩进。
> 语法：如：
              text-indent:20px;    向右缩进  
              text-index:-20px;     向左缩进
    值的单位：可以使em   1个em代表缩进一个文字的距离
              如：text-indent:2em;

> text-decoration:
>   作用：规定添加到文本的水平线
>   语法：
              text-decoration:none;              没有水平线的文本
              text-decoration:underline;       在文本下添加一条线
              text-decoration:overline;         在文本上添加一条线
              text-decoration:line-through; 穿过文本的一条线
# 2、CSS的背景样式属性
> background-color:
> 作用：设置元素的背景色
> 语法：
              background-color:颜色值;
background-image:
作用：设置元素的背景图
语法：
              background-image:url(图片路径);
案例：英雄联盟
background-repeat:
作用：设定背景图是否重复和如何重复
语法：
              background-repeat:repeat; 水平和垂直方向都重复，默认
              background-repeat:no-repeat; 背景图像仅仅显示一次
              background-repeat:repeat-x;   仅水平方向重复
              background-repeat:repeat-y;   仅垂直方向重复
案例：渐变背景
background-position:
 作用：设置背景图像的起始位置
 语法：
       background-position:水平方向值  垂直方向值;
 水平方向值：
   方位名词：left   center  right;
![](http://upload-images.jianshu.io/upload_images/5006978-dede4e25cedd3fea.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
垂直方向值：
方位名词：top          center   bottom
![](http://upload-images.jianshu.io/upload_images/5006978-a87057402bae4fc2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![](http://upload-images.jianshu.io/upload_images/5006978-ec1ea0fb2290fb45.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> background-attachment:
> 作用：
       设置背景图像是否固定或者随着页面的其余部分滚动。
语法：
       background-attachment:scroll;  滑动  默认
       background-attachment:fixed;   固定
背景属性联写：background
联写语法：
  background:颜色 背景图  是否重复和如何重复  滚动或固定 x位置  y位置
注意：
  需要什么就写什么，某些属性不写，也不会影响其他背景属性值

# 3、CSS三大特性
> 继承性：
> 概念：一个元素可以继承其父元素或祖先元素的样式。（子承父业）
> 哪些属性可以别继承？
       text-、font-、line-、color
注意：
        → a标签不能继承颜色color和text-decor。必须在a标签本身设定颜色
        → h标签不能被继承字体大小font-size。必须在h标签上设定字体大小。
![](http://upload-images.jianshu.io/upload_images/5006978-60524a36a8554b79.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 层叠性：
>    作用：是浏览器处理冲突的一个能力。
>    概念：
      如果一个属性通过两个选择器设置到同一个元素上面，那么这个时候
      一个属性就会将另一个属性层叠掉。
      如果多个不相同的属性通过两个选择器设置到一个元素上面，那么不
      会发生层叠。
> 优先级：
> 继承<通配符<标签选择器<类选择器<id选择器<行内style<!important
> !important ：
> 作用：
              可以使指定选择器里的某一个样式属性达到最优先。
注意：
       !important 虽然可以使我们的指定属性值达到最优先，但是在继承的样式属性同非继承的样式属性比较优先级时，继承的样式属性的优先级时最小的。
权重：
概念：优先级算法，层叠的规则。
作用：多个选择器组合以后的优先级。
算法：
       （0，0，0，0）==》第一个0对应的是!important的个数，第二个0对
       应的是id选择器的个数，第三个0对应的类选择器的个数，第四个0对
       应的是标签选择器的个数，就是当前选择器的权重。
比较：
       先从第一个0开始比较，如果第一个0大，那么说明这个选择器的权重
       高，如果第一个相同，比较第二个，依次类推。
              对于修饰的元素的样式属性，有两种情况，继承 和 非继承。
              非继承 要优先于 继承。
              若权重 一样（就近原则）
注意：选择器在查找元素的时候不是从左往右找，而是从右往左找。
![](http://upload-images.jianshu.io/upload_images/5006978-d8b9b50cf1349213.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
# 4、补充行高

![](http://upload-images.jianshu.io/upload_images/5006978-263c44312fc48071.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
> 行高的概念：
> 行高就是 文字的上间距 + 文字 + 文字的下间距。
> 注意：文字的上间距 和 文字的下间距是相等的
> 行高的作用：
> 可以同过设置文字行高（line-height）等于元素的高度(height)，使文字在元素中垂直居中。
> 行高中的单位：
>  px
       像素
 em
   和文字大小相关
   如：font-size:16px;  line-height:2em;
       2em 就是两个font-size的大小   32px
 %
   和em一样

> 浏览器默认文字的大小是16px
> 行高在不同浏览器下，甚至在不同系统的不同浏览器下，行高是不一致
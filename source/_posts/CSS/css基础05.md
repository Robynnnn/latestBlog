---
title: 05.CSS基础05
tags: CSS
categories: CSS
date: 2017-11-04
---
# 1、定位
> 定位，可以把盒子摆放到页面中任意位置的技术。
> 标签流：
> ![](http://upload-images.jianshu.io/upload_images/5006978-938dc9f974400c23.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
> 浮动:
> ![](http://upload-images.jianshu.io/upload_images/5006978-4cac73d592ec7423.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
> 定位：
> ![](http://upload-images.jianshu.io/upload_images/5006978-5d919d4db4ee4f5c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 1.2 定位的分类
> 静态定位【static】：默认的标准流定位方式。
> 绝对定位【absolute】：相对于浏览器边缘定位。
> 相对定位【relative】：相对于原来的位置定位。
> 固定定位【fixed】：相对于浏览器边缘定位，不随滚动条移动。

## 1.3 绝对定位
> 绝对定位：可以把一个盒子放在页面中任何一个位置，相对于“浏览器边缘”定位
> 属性：position: absolute;
> 特点：
> - 脱离标准流【飞起来】
> - 原位置丢失，后面元素补位
> - 随滚动条滚动
>   相对于“浏览器边缘”定位：
         水平移动：
                   left：离浏览器最左边的距离
                   right：离浏览器最右边的距离
         垂直移动：
                   top：离浏览器最上边的距离
                   bottom：离浏览器最下边的距离
## 1.4 相对定位
> 对定位：可以把一个盒子放在页面中任何一个位置，相对于“原位置”定位原位置：未定位之前所在的位置
> 特点：
> 1. 脱离标准流【飞起来】
> 2. 原位置保留
> 3. 随滚动条滚动
>    属性：position: relative;
>    坐标表示位置：
         水平移动：
                   left：离原位置左边的距离
                   right：离原位置右边的距离
         垂直移动：
                   top：离原位置上边的距离k
                   bottom：离原位置下边的距离
## 1.5 固定定位
> 固定定位：可以把一个盒子放在页面中任何一个位置，相对于“浏览器边缘”定位
> 特点：不会随着滚动条滚动
> 属性：position: absolute;
> 坐标表示位置：
         水平移动：
                   left：离浏览器最左边的距离
                   right：离浏览器最右边的距离
         垂直移动：
                   top：离浏览器最上边的距离
                   bottom：离浏览器最下边的距离
特点：
> 1. 脱离标准流【飞起来】
> 2. 原位置丢失，后面元素补位
> 3. 不会随滚动条滚动
## 1.6 元素层级
> 当多个元素互相覆盖时，它们之间的层级关系是：定位层>浮动层>标准流层
> 这个层级是固定的不能改变。

![](http://upload-images.jianshu.io/upload_images/5006978-504ef6a70bd1f5d1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
## 1.7 z-index
> 当定位的元素相互重叠时，可以通过z-index属性修改定位元素的上下级关系，值大的在上面。
> 注意：只对定位的元素有效。
> 如果多个元素被定位到同一个位置，那么默认情况下，在后面的盒子覆盖前面的盒子。

## 1.8 绝对变相对
> 一个绝对定位的元素是相对于浏览器边缘定位的，但是，当这个元素的上级元素中有一个元素是非静态定位的，那么这个元素会相对于这个上级元素定位。
> “一个元素相对于父级元素定位”.

# 2、页面布局
> ## 2.1 横向布局 ： inline-block vs float

> inline-block
> 问题：代码中的空格会显示在页面中，大小由字体和字尺寸决定
> 解决办法：
> 代码中去掉空格
> 代码中的空格变成注释
> margin负值

> float
> 问题：父元素会收缩
> 解决办法：为父元素添加clearfix类

> ## 2.2 垂直对齐
> 我们可以设置height等于line-height设置盒子内元素垂直居中对齐，但要注意几下几点：
> - 图片默认是以基线居中，设置图片的vertical-align: middle才可以实现中线居中
> - 非行级元素会继承line-height【框拉长】
> - 浮动的元素不受外层line-height的垂直居中影响【不能靠上级实现垂直居中，但通过本身的行高可以实现】
> - 设置vertical-align:middle时，非图片的inline-block的元素会向下移动
>   解决办法：设置行高小一些
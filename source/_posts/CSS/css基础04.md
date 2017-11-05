---
title: 04.CSS基础04
tags: CSS
categories: CSS
date: 2017-11-04
---
# 1、浮动
- 1.1 什么是浮动？
> 浮动，使一个盒子移动到父元素的最左边或者最右边的技术。
向左浮动：float: left;
向右浮动：float: right;

- 1.2 浮动的特点
  - 脱离标签流【向上飞起】
  - 原位置丢失，后面的元素补位  
  - 浮动到父元素的最左或者最右
  - 当有多个元素浮动时，连续向一个方向浮动的元素一个紧挨着一个跟在后面

- 1.3 浮动的应用

![](http://upload-images.jianshu.io/upload_images/5006978-d470cb8dc44a2fee.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](http://upload-images.jianshu.io/upload_images/5006978-2311d006a52e4c2e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](http://upload-images.jianshu.io/upload_images/5006978-22e13689cb4543bc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](http://upload-images.jianshu.io/upload_images/5006978-b5bbdf34727a357b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 2、清除浮动
> 当一个元素浮动时，后面的元素就会受其浮动的影响向前补位，如果不希望后面的元素受影响可以使用clear属性清除前面元素浮动对其的影响。
clear：left;   /* 清除左浮动的影响 */
clear：right;  /* 清除右浮动的影响 */
clear：both;  /* 清除左右浮动的影响 */

> 外层元素收缩的解决办法
当一个盒子里所有的元素都浮动起来之后，这个盒子就会收缩，显示出我们不希望要的效果：
浮动前： 
![](http://upload-images.jianshu.io/upload_images/5006978-6d775eb1dfda174d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
浮动后，外层元素收缩：
![](http://upload-images.jianshu.io/upload_images/5006978-ccc6d9477176bf65.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 原因：因为盒子里面所有元素都脱离了标准流，结果盒子里面变成“空”的了，所以就收缩了。
解决办法有很多种：

    1. 设置明确的高
    2. 设置父元素overflow: hidden;
    3. 添加额外元素法
  >  在盒子最后添加一个空的高度为0的div并设置其清除左右浮动：
   <div style=”clear: both”></div>
   > 4. 使用:after伪类
定义CSS类：
.clearfix:after {content:"\200B"; display:block; height:0; clear:both; }
.clearfix { *zoom:1; } /* 解决IE6下不好使的问题 */
为父元素增加类：
<div class=”clearfix”>...</div>
# 3、盒子宽、高的计算方式
> box-sizing：盒子如何计算宽、高。
box-sizing: content-box;【默认】：宽=width+左内边距+右内边距+左边框+右边框
box-sizing: border-box; 宽=width   高=height
这个属性在IE6，7中不能使用，在firefox2.0~28需要添加-moz-前缀，chrome4.0~9.0需要添加-webkit-前缀：

![](http://upload-images.jianshu.io/upload_images/5006978-62366f72bedc16f1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
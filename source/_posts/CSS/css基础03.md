---
title: 03.CSS基础03
tags: CSS
categories: CSS
date: 2017-11-04
---
# 1、盒子模型
- 1.1 生活中的盒子

![](http://upload-images.jianshu.io/upload_images/5006978-35f99e17dde60c4c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](http://upload-images.jianshu.io/upload_images/5006978-fe5d2837947799b8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
> 生活中的盒子模型：
      → 盒子的边框的厚度，外壳。
      → 盒子中的填充物，泡沫。
       → 盒子中的内容，手机。
       → 盒子与盒子之间的距离。

- 1.2 CSS中的盒子模型

![](http://upload-images.jianshu.io/upload_images/5006978-56b67d60db32157a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](http://upload-images.jianshu.io/upload_images/5006978-5e9482b0f996af90.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
> 在web中，我们在body里所放到任何元素都可以看成一个盒子，所以在网页中“万物皆是盒子”。
> CSS中的盒子模型：
      → 元素（盒子）的边框，border。相当于生活中盒子的外壳的厚度。
       → 元素（盒子）的内边距，padding。 相当于生活盒子里的泡沫。
      → 元素（盒子）的内容区域width、height值。相当于生活中盒子里中的手机。
       → 元素（盒子）的外边距margin。相当生活中盒子与盒子之间的距离

# 2、CSS 盒子模型中的边框（border）
> border样式属性：
>   作用：设置盒子的边框相关样式
         border-width：边框的厚度或大小
                            如：border-width:1px;
  border-style：边框的类型
                            如：border-style:值;
                                   none      无边框 默认
                                   solid  实线
                                  dotted 点状边框
                                  dashed 虚线
                                   double 双边框
                             ...
         border-color：边框的颜色
                            如：border-color:red;
                            若不设置边框的颜色，默认为黑色。
         联写：
                      border:边框的大小 边框的类型 边框的颜色;
                如：border:1px solid blue;


> 盒子的四个边框：
      边框的方向：top上、right右、bottom下、left左
       单个方向设置：
              border-方向:边框厚度  边框的类型  边框的颜色。
              如：border-top:10px  solid  red;

注意：

      →   一般情况下，边框会影响盒子的大小。
      → 默认情况下，针对块级元素，若不设置width时，该块级元素的width等于它父元素的width。
              对于子元素，增加边框时，该元素的width会自动改变适应父元素的区域。
> 表格边框合并：
              border-collapse:collapse

# 3、CSS盒子模型中的内边距（padding）
> 内边距会影响盒子的大小！因为会把盒子撑大，
> 因为整体的宽=width+左右的内边距
> 整体的高：height+上下边距
> 如果不想计算，可以直接用一个属性：border-sizing:borer-box;
> border-sizing: border-box;
> /*但是弊端是有很多浏览器不支持*/
> -moz-border-sizing: border-box;
> -webkit-border-sizing: border-box;
> /*为避免不必要的麻烦，直接以上代码全部敲*/

> 用webstorm的话，输入bx+table就行
> padding样式属性：
      作用：设置盒子中的内边距
       语法：
                     padding:数值;
                     如：padding:20px;
注意：
       → 一般情况下，边框会影响盒子的大小。
              → 默认情况下，针对块级元素，若不设置width时，该块级元素的width等于它父元素的width。
              对于子元素，增加内边距时，该元素的width会自动改变适应父元素的区域。
当一个盒子设置了背景图片logo后，盒子里面的文字默认是压在图片上面的，如果想显示出logo，可以考虑用padding解决问题。
盒子的四个内边距：
      内边距的方向：top上、right右、bottom下、left左
      语法：
         padding-方向:值;
               如：padding-left:20px;
       联写：
                padding:值1
                     值1:（上、右、下、左）
              如:  padding:10px;
    
         padding:值1 值2;
                            值1（上、下）
                     值2（左、右）
              如:  padding:10px  20px;


                padding:值1 值2 值3;
                            值1（上）
                            值2（左、右）
                            值3（下）
              如:  padding:10px  20px  10px;


                padding:值1 值2 值3 值4；
                            值1（上）
                            值2（右）
                            值3（下）
                            值4（左）
                            如： padding:10px  20px  10px  20px;


> 注意：
              针对行级元素，在设定其padding值时，在IE浏览器低版本中（IE8以下），padding的上下没有效果。
# 4、盒子的总大小
> 盒子的大小：
       盒子的总宽度：内容区域width + 左右内边距padding + 左右边框border
       盒子的总高度：内容区域height + 上下内边距padding + 上下边框border

![](http://upload-images.jianshu.io/upload_images/5006978-2e40e5d6cc821299.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 5、盒子的外边距margin
> margin样式属性：
      作用：设置盒子与其他盒子之间的距离。
       语法：
                     margin:数值;
                     如：margin:20px;
注意：
       → margin的改变不会影响盒子的大小。


> 盒子的四个外边距：
      外边距的方向：top上、right右、bottom下、left左
      语法：
         margin-方向:值;
               如：margin-left:20px;
       联写：
                margin:值1
                     值1:（上、右、下、左）
              如:  margin:10px;
    
         margin:值1 值2;
                            值1（上、下）
                     值2（左、右）
              如:  margin:10px  20px;


                margin:值1 值2 值3;
                            值1（上）
                            值2（左、右）
                            值3（下）
              如:  margin:10px  20px  10px;


                margin:值1 值2 值3 值4；
                            值1（上）
                            值2（右）
                            值3（下）
                            值4（左）
                            如： margin:10px  20px  10px  20px;
> 盒子水平居中：
              margin:0px  auto;
注意：盒子必须是块级元素，且宽度必须确定。
margin的特殊情况一：
              针对行内元素，margin的上下没有效果。

> margin的特殊情况二：
             对于一个父元素里所嵌套的子元素。若父元素没有上边框没有上内边距，设置子元素的margin-top值时，margin-top对子元素无效，并且父元素会受到影响。 解决办法就是给父元素加个上边框或上内边距。
              这种情况，我们在实际开发中，一般不会选择用子元素margin-top，而会用父元素的padding-top来实现。

> margin的特殊情况三（margin合并或塌陷问题）：
              对于两个同级的盒子，一个在上一个在下。若上面的盒子margin-bottom与下面的盒子margin-top一起作用时。这时，上下两个盒子的间距会选择margin-bottom 与 margin-top中最大的值。
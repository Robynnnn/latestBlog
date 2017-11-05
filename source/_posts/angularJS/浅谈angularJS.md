---
title: 浅谈angularJS
tags: angularJS
categories: angularJS
date: 2017-11-2
---

-  #####   1  Angular简称NG

- #####   2 Angular的重要特性
    -  MVC: 在前端引入了MVC的设计模式.
    -  模块化开发
    -  自动的双向数据绑定
    -  语义化标签(自定义标签)
    -  依赖注入
    -  其核心就是通过指令扩展了HTML,通过表达式绑定数据到HTML
    -  Angular不推崇DOM操作,也就是说在NG中几乎找不到任何的DOM操作.
    -  ng最主要是用来实现spa应用. - 单页面应用程序


-  #####   3 下载方式
> 1.官方网站下载：
> [https://angularjs.org/](https://angularjs.org/)
> 2. npm下载：
>    npm install angular
> 3. 通过bower下载：
>    bower install angular

-  #####   4 代码中的MVC
- 我们将我们的代码分为三部分
   -  M - Model 数据 数据实体,用来保存页面要展示的数据.
   -  V - View 视图 负责显示数据的,一般其实就是指的html页面.
   -  C - Controller 控制器 控制整个业务逻辑,负责处理数据,比如数据的获取,以及数据的过滤，进而影响数据在视图上的展示.
- 这样,这3部分各司其职,分工合作,我们的代码就会变得更有层次并容易维护.
- 这样的程序设计模式,我们就叫做MVC设计模式.
- 所以,MVC并不是一个新的知识点,而是一个新的写代码的套路.


![架构](http://upload-images.jianshu.io/upload_images/5006978-61df8c64e4c267b2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

-  MVC是由后端而来,由于受到前端技术的限制便有了一些细节的调整，进而出现了很多MVC的衍生版（子集）-  如MVVM、MVW、MVP、MV*等。
- 注：做为初学可以不必过于在意这些概念。

- #####   5  模块化
- 使用AngularJS构建应用（App）时是以模块化（Module）的方式组织的，即将整个应用划分成若干模块，每个模块都有各自的职责，最终组合成一个整体。
- 采用模块化的组织方式，可以最大程度的实现代码的复用，可以像搭积木一样进行开发。

- #####   5.1 定义应用  
- 通过为任一HTML标签添加ng-app属性，可以指定一个应用，表示此标签所包裹的内容都属于应用（App）的一部分。通俗的理解就是: ng-app属性标签被Angular管理，包括其中的子标签.Angular会认为这是一个应用，将其作为一个应用来看待。

~~~
<!-- 为html标签添加ng-app表明整个文档都是应用 -->
<!-- ng-app属性可以不赋值，但是要关联相应的模块时则必须赋值 -->
<html lang="en" ng-app="App">
~~~

-  #####   5.2 定义模块
   -  AngularJS提供了一个全局对象angular,调用该全局对象的module()方法可以创建一个模块.该方法返回一个模块对象.这个模块对象就是AngularJS用来管理应用的对象.
~~~
 <!DOCTYPE html>
  <!--为html标签定义ng-app属性 代表整个文档都被ng管理-->
  <html lang="en" ng-app="myApp">
  <head>
      <meta charset="UTF-8">
      <title>Title</title>
      <script src="lib/angular.js"></script>
  </head>
  <body>

  <script>
      //调用全局对象angular的module方法创建一个模块.
      //第一个参数: 模块要管理的标签范围,写上ng-app属性的值.
      //第二个参数: 模块依赖,数组,如果不需要依赖,就直接写一个空数组就可以.
      //返回值:返回的app对象,我们可以认为这个对象就是用来管理这个模块的.
      var app = angular.module('myApp',[])
  </script>
  </body>
  </html>
~~~

-  #####   5.3 定义控制器
   -  接下来我们可以通过app模块对象来创建控制器.
   -  调用app模块对象的controller方法，就可以创建控制器. 

~~~
//调用全局对象angular的module方法创建一个模块.
  //第一个参数: 模块要管理的标签范围,写上ng-app属性的值.
  //第二个参数: 模块依赖,数组,如果不需要依赖,就直接写一个空数组就可以.
  //返回值:返回的app对象,我们可以认为这个对象就是ng用来管理这个模块的.
  var app = angular.module('myApp',[])

  //调用app的controller方法创建控制器.
  //第一个参数: 要将创建的控制器关联到指定的View上，字符串.
  //第二个参数: 这是一个数组,数组的其中一个元素是'$scope',
  //           数组的最后一个元素必须是1个function 参数是$scope
  //           先这么认为,就这么死写,后面会解释原因.
  app.controller('demoCtrl',['$scope',function ($scope) {

  }]);
~~~

-  但是这个时候,我们只是创建了控制器,并没有将控制器和视图关联起来.
   -  视图是用来负责显示数据的,控制器是来处理数据模型,并将数据模型给视图展示.
   -  视图就是我们的html页面. 所以我们可以指定1个html元素(视图)与这个控制器相关联.
   -  为这个html元素指定1个ng-controller属性.值为创建controller的第1个参数的值.

~~~
 <div ng-controller="demoCtrl"> <!-- 这个时候,创建的控制器，就与这个视图关联起来了. -->
      <dl>
          <dt></dt>
          <dd></dd>
      </dl>
  </div>
~~~
-    这个时候,创建的控制器，就与这个视图关联起来了
   - 在控制器中就可以处理制造数据.视图中就可以显示模型数据了.

- #####   5.4  数据模型
   - 控制器负责处理制造模型数据.
   - 视图负责显示控制器制造的模型数据.
   - 那么控制器如何制造数据呢?
~~~
app.controller('demoCtrl',['$scope',function ($scope) {
  //我们可以认为,$scope就是一个数据模型.
  //这是一个对象，
  //这个对象可以在控制器中访问,也可以在与控制器关联的视图中直接访问.
  //那么这个时候,控制器中可以将制造的数据放在这个$scope对象中.
  $scope.name = '小明';
  $scope.info = '我在黑马跟着老王学习前端开发';
  }]);
~~~

-  这个时候,控制器已经负责将数据模型构建完毕,那么视图中如何展示这些数据呢?

~~~
 <!-- 这个视图与我们创建的控制器相关联
    在这个视图中，可以直接访问与之相关联的控制器
    构建的$scope对象。需要注意的是，
    在视图中，如果要绑定显示$scope对象中的数据的值：
    a. 使用{{  }}符号。
    b. 在这其中直接写上$scope对象的属性名就可以。
    {{ name }}不需要写$scope.name,而是直接写name
    c. 这样在ng渲染的时候，就会将{{ name }}显示成$scope.name的值。
   -->

  <div ng-controller="demoCtrl">
    <dl>
      <dt>{{ name }}</dt>
      <dd>{{ info }}</dd>
    </dl>
  </div> 
~~~

### 总结


![总结](http://upload-images.jianshu.io/upload_images/5006978-3d7be2928da29dfc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
---
title: CSS鼠标悬浮之后整个框浮起来的效果
tags: CSS
categories: CSS
date: 2020-04-17
---

```less
.productsShow>li {
    -webkit-transition: .6s;
    transition: .6s;
}

.productsShow>li:hover {

 -webkit-transform: translateY(-4px); 
 transform: translateY(-4px); 
 -webkit-animation-fill-mode: forwards; 
 animation-fill-mode: forwards; 
 -webkit-box-shadow: 0 40px 50px rgba(0,0,0,.25);
 box-shadow: 0 40px 50px rgba(0,0,0,.25);
}

```
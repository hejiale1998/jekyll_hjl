---
title: helloblog
date: 2017-11-16
tags:
---
###### 引用
> It never will rain roses. When we want to have more roses we must plant trees.

[链接这样写](http://www.baidu.com)
![我喜欢的图片](./images/11-16.jpg)

<font color=#0ff size=7>es6</font>
### 新增加了let和const声明
#####  let 不存在变量声明提升，不能重复声明变量； const一旦声明常量的值就不能更改,声明一个常量必须马上初始化,不能重复声明，引用类型变量 变量名不指向数据，而是指向数据所在的地址 
```{bash}.
const foo = {};
foo.prop = 123;  //对象内部属性值都是可以变得但是引用的地址不能变
foo = {};  //报错
```
### 块级作用域
##### 特点 
##### let声明变量 声明周期为块级作用域内（里面能用外面，外面不能用里面）；一旦let在作用域中声明变量 就将统治这个作用域
```{bash}.
var a = 1;
{
    console.log(a);
    let a = 2;
 }       //会报错
```
##### 优势
##### 1.可以代替匿名函数
```{bash}.
    var oDiv = document.getElementsByTagName('div');
    // for(var i = 0; i < oDiv.length; i ++) {
    //     (function (i) {
    //         oDiv[i].onclick = function () {
    //             console.log(i);
    //         }
    //     }(i))
    // }
    for(let i = 0; i < oDiv.length; i ++) {
            oDiv[i].onclick = function () {
                console.log(i);
            }
    }     
```
##### 2.防止变量污染
##### const一旦声明常量的值就不能更改；声明一个常量必须马上初始化；不能重复声明
### 解构赋值
##### ES6允许按照一定模式，从数组和对象中提取，对（var let const）变量进行赋值，这被称为解构。
##### 1、模式匹配  const [a, b ,c] = [1, 2, 3];&nbsp; &nbsp; &nbsp; &nbsp;//解构赋值必须模式匹配，如左边是数组右边不能是原始值  
##### 2、解构失败就是undefined-->右面的值少&nbsp; &nbsp; &nbsp; &nbsp; //var [bar,foo2] = [1];

##### 3、不完全解构-->右面的值多&nbsp; &nbsp; &nbsp; &nbsp; //let [x,y] = [1,2,3];
#### 默认赋值（只有右侧的值严格等于undefined才生效）  &nbsp; &nbsp; &nbsp; //var [foo = true] = [];
#### 默认赋值可以应用解构赋值的其他变量
##### 首先看右侧有无和左侧对应的值，没有的话看左侧从左到右解析
#####  let [x4 = y4, y4 = 1] = [];<font color=#7EC0EE size=3>&nbsp; &nbsp; &nbsp; &nbsp;//会报错，y4 is not defined</font>
#####  let [x2 = 1, y2 = x2] = [2];&nbsp; &nbsp; &nbsp; &nbsp;//2 2
##### ·对象的解构赋值
![对象](/images/解构1.png)
##### 字符串的解构赋值--- >字符串会转化成一个类数组的对象    const [a,b,c,d,e] = 'hello';&nbsp; &nbsp; console.log(a,b,c,d,e);&nbsp; &nbsp; &nbsp; &nbsp; //h e l l o

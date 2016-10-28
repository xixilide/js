## 数组去重
思路：
1.创建一个新的数组存放结果
2.创建一个空对象
3.for循环时，每次取出一个元素与对象进行对比，如果这个元素不重复，则把它存放到结果数组中，同时把这个元素的内容作为对象的一个属性，并赋值为1，存入到第2步建立的对象中。
说明：至于如何对比，就是每次从原数组中取出一个元素，然后到对象中去访问这个属性，如果能访问到值，则说明重复。
复制代码 代码如下:
```js
Array.prototype.unique3 = function(){
 var res = [];
 var json = {};
 for(var i = 0; i < this.length; i++){
  if(!json[this[i]]){
   res.push(this[i]);
   json[this[i]] = 1;
  }
 }
 return res;
}
var arr = [112,112,34,'你好',112,112,34,'你好','str','str1'];
alert(arr.unique3());
```
### JS框架
1. Jquery ：

jQuery是一款同prototype一样优秀js开发库类，特别是对css和XPath的支持，使我们写js变得更加方便！如果你不是个js高手又想写出优 秀的js效果，jQuery可以帮你达到目的！并且简介的语法和高的效率一直是jQuery追求的目标，

优点：注重简介和高效，js效果有yui-ext的选择，因为yui-ext 重用了很多jQuery的函数

缺点：据说太嫩，历史不悠久。

2. Mochikit ：

MochiKit自称为一个轻量级的js框架。MochiKit 主要受到 Python 和 Python 标准库提供的很多便利之处的启发，另外还缓解了浏览器版本之间的不一致性。其中的 MochiKit.DOM 尤其方便，能够以比原始 JavaScript 更友好的方式处理 DOM 对象。MochiKit.DOM 大部分都是针对 XHTML 文档定制的，如果与 MochiKit 和 Ajax 结合在一起，使用 XHTML 包装的微格式尤其方便。Mochikit可以直接对字符串或者数字格式化输出，比较实用和方便。它还有自己的 js 代码解释器

优点：MochiKit.DOM这部分很实用，简介也是很突出的

缺点：轻量级的缺点

### css框架
- Blueprint
是比较早的，基于静态css的框架。但是现在有两个主要的动态css语言，LESS和SASS，给css提供了变量，mixin，运算符等功能，让写出模块化的css框架成为可能。

- Bootstrap
现在基本是欧美这里最流行的框架，基于LESS，最近升级2.0以后完全模块化，也不需要太多配置，很好用。这个框架对大部分元素的视觉细节都已经做得很完整，基本上你只需要写html，加几个class，就可以做出像模像样的页面了，做起prototype来嗷嗷快。不过这也是个缺点，因为用的人多了样式都长一个样... 当然，模块化的框架你要修改起来也是很方便的，基本上修改变量就可以了。

- Compass
另一个比较流行的是基于SASS的Compass，这个框架包含了Blueprint作为其中的一个模块。需要注意的是这个框架和Ruby on Rails是高度整合的，用起来需要大量的命令行操作，比Bootstrap麻烦，但是在Rails开发人员里面用得比较多。

### 鸡蛋形状的css
```
border-radius: 50% 50% 50% 50% / 62% 62% 38% 38%;
```
### 5.编程题：实现随机选取10–100之间的10个数字，存入一个数组，并排序。
```js
var arr=[];
for(var i=0;i<10;i++){
  arr.push((Math.floor(Math.random()*10)+1)*10);
}
function compare(value1,value2){
   if(value1<value2){
     return -1;
   }else if(value1>value2){
      return 1;
   }else{
     return 0;
   }
}
console.log(arr.sort(compare));
```
### 如何获得大于0小于9的随机数
```js
function randomMath() {
return Math.floor(Math.random()*10);//0-9
}
```
### 编写程序实现多态  (关于java的题)

多态：对于多态的实现，有三个关键字new，virtual，override的使用，多态可以简 单的理解为对不同的对象调用相同的方法，表现出不同的行为，这种特性是通过继承来实现的。

例1
：
```
public class Animal      {  
          public virtual void Eat()          {   
                        Console.WriteLine("Animal eat");     
                             }      }   
          public class Cat : Animal      {   
               public override void Eat()          {           
                  Console.WriteLine("Cat eat");        
                    }      }    
           public class Dog : Animal      {       
                public override void Eat()          {   
                    Console.WriteLine("Dog eat");       
                       }      }    
    class Tester      {        
        static void Main(string[] args)       
           {   
             Animal[] animals = new Animal[3];     
             animals[0] = new Animal();       
             animals[1] = new Cat();           
             animals[2] = new Dog();           
             for (int i = 0; i < 3; i++)         
             {                   
               animals[i].Eat();     
                  }  
                }   
   }  
```
 输出如下：  Animal eat... Cat eat... Dog eat...  

在上面的例子中，通过继承，使得Animal对象数组中的不同的对象，在调用Eat()方法时，表现出了不同的行为。  


### 1.js中有哪些数据类型，并解释清楚原始数据类型和引用数据类型

js中共有null,undefined, string,number,boolean,object六种数据类型。

原始数据类型: null,undefined, string,number,boolean

引用数据类型:object

两者的区别：
1）值存储方式不同：
原始数据类型：将变量名和值都存储在栈内存中
引用数据类型：将变量名存储在栈内存中，将值存储在堆内存中，并在栈内存中存储值的地址，该地址指向堆内存中的值。

2）赋值方式不同：

当给b赋予另一个a的值
若a值为原始数据类型，直接在栈内存中生成b值，两个变量以后进行值改变不会相互影响

若a值为引用数据类型，赋予b变量的是值地址，通过这个地址，两者指向的其实是堆内存中的同一个值，所以以后a,b任一变量对值进行改变，会直接影响另一个变量的值

### 2. 解释清楚 null 和 undefined

null表示一个标识被赋值了，且该标识赋值为“空值”,从逻辑角度来看，null值表示空对象指针；

undefined表示声明了标识，但没有给标识赋值。
### 3. 如何复制一个对象的值？

```js
function cloneObject(object){
   var newObject = new Object();


   for(var i in object){
      newObject[i] = object[i];
    }
    return newObject;
 }
```

### 4. js在什么时候会进行隐式类型转换，转换的结果？

 数值运算
 if
 .调用方法或属性
 !和!!

### 5. 类型识别的方法？
typeof a

可以判别标准类型，除了null之外

typeof 1 返回结果："number"typeof {} 返回结果:"object"

不能判别具体的对象类型，除了function之外

typeof [1] 返回结果:"object"typeof function(){} 返回结果:"function"

a instanceof b

可以判别内置对象类型

[] instanceof Array 返回结果：true new String() instanceof String返回结果：true

不能判别原始类型值

'a' instanceof String 返回结果：false

可以判别自定义对象类型
```js
 function Point(x,y){
    this.x = x;
     this.y = y
     } var c = new Point(1,2)
      c instanceof Point
```
      返回结果：true

      a.constructor
      可以判别标准数据类型（undefined和null除外）

      '123'.constructor == String 返回结果：true

      可以判别具体的内置对象类型
      [1,2].constructor == Array返回结果：true

      可以判别自定义对象类型

```js
       function Point(x,y){
          this.x = x;
           this.y = y
           }
            var c = new Point(1,2)
            c.constructor == Point
```

            返回结果：true

            Object.prototype.toString.call(a)
            可以判别标准数据类型

            Object.prototype.toString.call(1)返回结果:"[object Number]" Object.prototype.toString.call(undefined) 返回结果:"[object Undefined]"
            可以判别内置对象类型
            Object.prototype.toString.call([a]) 返回结果:"[object Array]"

            不能判别自定义对象类型
            ```js
            function Point(x,y){
              this.x = x;
              this.y = y
            }
            var c = new Point(1,2)
            Object.prototype.toString.call(c)
            ```
            返回结果:"[object Object]"

            工作中可以写一个函数方便判定
            function type(obj){<br>return Object.prototype.toString.call(obj).slice(8,-1)
              }
              type('a') 返回结果: "String" type([a])返回结果: "Array"
              函数

#### 1. 函数里的this什么含义，什么情况下，怎么用?

              谁调用的方法或者属性，this就指向谁

              如果没有被谁调用，this指向window


#### 2. bind,call,apply方法的使用，什么区别,  什么时候用?

#### 3. 函数curry化

    函数curry化是什么意思？
              把接受多个参数的函数转换为接受单一参数的函数，且函数可以持续接收参数

              将一个复杂的问题片段化，使之进行简化
#### 3. 数组和对象有哪些原生方法，列举一下，分别是什么含义，比如链接两个数组用哪个方法，删除数组的指定项。
原型
### 1. 讲一下 prototype 是什么东西，原型链的理解，什么时候用 prototype?
proto
构造函数

闭包
1.什么是闭包？
2.闭包的作用和使用场景

闭包的作用一：隐藏、封装

闭包的作用二：记忆函数

### 变量作用域
ajax

1. 讲解原生Js实现ajax的原理。

　　Ajax 的全称是Asynchronous JavaScript and XML，其中，Asynchronous 是异步的意思，它有别于传统web开发中采用的同步的方式。

　　Ajax的原理简单来说通过XmlHttpRequest对象来向服务器发异步请求，从服务器获得数据，然后用javascript来操作DOM而更新页面。

　　XMLHttpRequest是ajax的核心机制，它是在IE5中首先引入的，是一种支持异步请求的技术。简单的说，也就是javascript可以及时向服务器提出请求和处理响应，而不阻塞用户。达到无刷新的效果。

　　XMLHttpRequest这个对象的属性有：

onreadystatechange每次状态改变所触发事件的事件处理程序。

 responseText从服务器进程返回数据的字符串形式。

  responseXML从服务器进程返回的DOM兼容的文档数据对象。

   status从服务器返回的数字代码，比如常见的404（未找到）和200（已就绪）

    status Text伴随状态码的字符串信息

     readyState对象状态值

      0 (未初始化) 对象已建立，但是尚未初始化（尚未调用open方法）

       1 (初始化) 对象已建立，尚未调用send方法

       2 (发送数据) send方法已调用，但是当前的状态及http头未知

       3 (数据传送中) 已接收部分数据，因为响应及http头不全，这时通过responseBody和responseText获取部分数据会出现错误，

       4 (完成) 数据接收完毕,此时可以通过通过responseXml和responseText获取完整的回应数据

### 实现加法代码如下：

```js
       add(2, 5); // 7

       add(2)(5); // 7

       function addto(){

         var length = arguments.length;
         var sum = 0;
         for(var i = 0;i&lt;length;i++){
           sum += arguments[i]
         }
         return sum;
       }
       function add(){
         var value = addto.apply(add,arguments);
         var helper = function(next){
           typeof next == "number" ? value+=next:value;
           return helper
         }
         helper.valueOf = function(){
           return value;
         }
         return helper;
       }
  ```
#### 如何使用javascript 方法duplicate，使（[1,2,3,4,5]）返回结果为[1,2,3,4,5,1,2,3,4,5]


```js
  duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]

  function duplicate(arr){
    var length = arr.length;
       for(var i=0;i<length;i++)
      arr.push(arr[i])
         return arr;
            }
  ```


#### 4.想要去除一个字符串的第一个字符，有哪些方法可以实现.
```js
 str.slice(1)
str.substr(1)
str.substring(1)
str.replace(/./,'')
str.replace(str.charAt(0),'')
```

### 5.对一个数组（每项都是数值）求和，有哪些方法？

### JS中的call、apply、bind方法

一、call()和apply()方法

1.方法定义

call方法:

语法：call([thisObj[,arg1[, arg2[,   [,.argN]]]]])

定义：调用一个对象的一个方法，以另一个对象替换当前对象。

说明：

call 方法可以用来代替另一个对象调用一个方法。call 方法可将一个函数的对象上下文从初始的上下文改变为由 thisObj 指定的新对象。

如果没有提供 thisObj 参数，那么 Global 对象被用作 thisObj。

apply方法：

语法：apply([thisObj[,argArray]])

定义：应用某一对象的一个方法，用另一个对象替换当前对象。

说明：

如果 argArray 不是一个有效的数组或者不是 arguments 对象，那么将导致一个 TypeError。

如果没有提供 argArray 和 thisObj 任何一个参数，那么 Global 对象将被用作 thisObj， 并且无法被传递任何参数。

c、实现继承

function Animal(name){	  
	this.name = name;	  
	this.showName = function(){	  
		alert(this.name);	  
	}	  
}	  
function Cat(name){
	Animal.call(this, name);
}	  
var cat = new Cat("Black Cat");	 
cat.showName();
Animal.call(this) 的意思就是使用 Animal对象代替this对象，那么 Cat中不就有Animal的所有属性和方法了吗，Cat对象就能够直接调用Animal的方法以及属性了.

二、bind

在EcmaScript5中扩展了叫bind的方法（IE6,7,8不支持），使用方法如下
```js
function T(c) {
	this.id = "Object";
	this.dom = document.getElementById("scroll");
}
T.prototype = {
	init: function() {
	   //①
		this.dom.onmouseover = function() {
			console.log("Over-->"+this.id);
		}
	   //②
		this.dom.onmouseout = function() {
			console.log("Out -->"+this.id);
		} .bind(this)
	}
};
(new T()).init();
```
结果：

通过①和②的对照加上显示的结果就会看出bind的作用：改变了上下文的this

bind与call很相似,，例如，可接受的参数都分为两部分，且第一个参数都是作为执行时函数上下文中的this的对象。

不同点有两个：

①bind的返回值是函数

//都是将obj作为上下文的this
```js
function func(name,id) {
    console.log(name,id,this);
}
var obj = "Look here";
//什么也不加func("    ","-->");

//使用bind是 返回改变上下文this后的函数

var a = func.bind(obj, "bind", "-->");

a();

//使用call是 改变上下文this并执行函数

var b = func.call(obj, "call", "-->");
```
结果：


②后面的参数的使用也有区别
```js
function f(a,b,c){
    console.log(a,b,c);
}

var f_Extend = f.bind(null,"extend_A")
f("A","B","C")  //这里会输出--> A B C

f_Extend("A","B","C")  //这里会输出--> extend_A A B

f_Extend("B","C")  //这里会输出--> extend_A B C

f.call(null,"extend_A") //这里会输出--> extend_A undefined undefined
```
call 是 把第二个及以后的参数作为f方法的实参传进去

而bind 虽说也是获取第二个及以后的参数用于之后方法的执行，但是f_Extend中传入的实参则是在bind中传入参数的基础上往后排的。

//这句代码相当于以下的操作
```js
var f_Extend = f.bind(null,"extend_A")

//↓↓↓

var f_Extend = function(b,c){
    return f.call(null,"extend_A",b,c);
}
```
举一个应用场景：例如现在有一个方法 根据不同的文件类型进行相应的处理，通过bind 就可以创建出简化版的处理方法
```js
function FileDealFunc(type,url,callback){
	if(type=="txt"){...}
	else if(type=="xml"){...}
	.....
}
var TxtDealFunc = FileDealFunc.bind(this,"txt");
//这样使用的时候更方便一些

FileDealFunc("txt",XXURL,func);  //原来

TxtDealFunc(XXURL,func); //现在
```

## ＪＳ基础
### 1. 变量
  - 变量可以使用短名称（比如 x 和 y），也可以使用描述性更好的名称（比如 age, sum, totalvolume）。
  - 变量必须以字母开头
  - 变量也能以 $ 和 _ 符号开头（不过我们不推荐这么做）

    变量名称对大小写敏感（y 和 Y 是不同的变量）

    您可以在一条语句中声明很多变量。该语句以 var 开头，并使用逗号分隔变量即可：
    var name="Gates", age=56, job="CEO";
    声明也可横跨多行：
    var name="Gates",
    age=56,
    job="CEO";

### 2. 标志符

### 3. 数据类型、字符串　数字　boolean undefinde 对象

### 4. 数据类型转换　String() Number()

### 5. 运算符　+ - * / % ==  ===
      == 数字相等

      === 数值和数据类型都相等
      a>5 ?
 if else switch

### 6.循环语句

```js
//从1 加到 100
var r = 0;
for (var i = 0; i <= 100; i++) {
  r = r + i;

}
console.log(r);
```
### 作用域 变量提升

```js
var a=10;//全局变量
function fun() {
console.log(a);  
var a = 20;//局部变量
}
fun();
//输出a = 10;
```

```js
var v='Hello World';
(function(){
var v;
alert(v);
v='I love you';
})()
//弹出undefined
```
所以，才会提示说“undefined”。

从这里，我们也学习到，我们在写js code 的时候，我么需要把变量放在块级作用域的顶端，防止出现意外。

在我们写js code 的时候，我们有2种写法，一种是函数表达式，另外一种是函数声明方式。我们需要重点注意的是，只有函数声明形式才能被提升。
变量声明，命名，和提升
在javascript，变量有4种基本方式进入作用域：

- 1 语言内置：所有的作用域里都有this和arguments；(译者注：经过测试arguments在全局作用域是不可见的)
- 2 形式参数：函数的形式参数会作为函数体作用域的一部分；
- 3 函数声明：像这种形式：function foo(){}；
- 4 变量声明：像这样：var foo；
函数声明和变量声明总是会被解释器悄悄地被“提升”到方法体的最顶部。

### 7. 对象
    内置对象、　自定义对象　、　浏览器对象

    JavaScript 中的所有事物都是对象：字符串、数字、数组、日期，等等。
　　　　在 JavaScript 中，对象是拥有属性和方法的数据。

举例：汽车就是现实生活中的对象。
汽车的属性：
car.name=Fiat

car.model=500

car.weight=850kg

car.color=white
汽车的方法(行为)：
car.start()

car.drive()

car.brake()
汽车的属性包括名称、型号、重量、颜色等。
所有汽车都有这些属性，但是每款车的属性都不尽相同。
汽车的方法可以是启动、驾驶、刹车等。
所有汽车都拥有这些方法，但是它们被执行的时间都不尽相同

#### 自定义对象
```js
 var obj = {
       name:"sansan",
       ade:"12",
       sayName:function () {
         console.log("我叫": +this.name);
         //对象才有属性，this 指当前的对象　相当于obj.name
       }
     }
    obj.sayName();//调用函数
    obj.name;
```
#### 传参
```js
function say(name,age){
  console.log("名字："+name+"年龄："+age);
}
say("zhaosi","11");
```
#### 返回值
```js
function fun() {
  var a=1;
  var b=2;
  return a+b
}
console.log(fun());//结果为返回结果
```
注：执行完return 后跳出函数执行了

### 8.数组
```js
var arr = [1,2,3,4,5,6,7,8,9,10];
var arr1 = new Array(1,2,3,4,5,6,7,8,9,10);
console.log(arr);//Array[10]
console.log(arr1);//Array[10]
//可修改数组
arr[3]=7;
console.log(arr);
```
数组对象方法：

- 使用 concat() 方法来合并两个数组。

  var arr = arr1.concat(arr3,arr2);

- push()向数组的末尾添加一个或更多元素，并返回新的长度。

  arr1.push("9","4");

- pop() 方法用于删除并返回数组的最后一个元素。
    arr1.pop()

- shift() 方法用于把数组的第一个元素从其中删除，并返回第一个元素的值。

- unshift() 方法可向数组的开头添加一个或更多元素，并返回新的长度

    语法
    arrayObject.unshift(newelement1,newelement2,....,newelementX)

    打印出的是返回值，数组长度
- valueOf() 方法返回 Array 对象的原始值。

  该原始值由 Array 对象派生的所有对象继承。

  valueOf() 方法通常由 JavaScript 在后台自动调用，并不显式地出现在代码中。

- splice() 方法向/从数组中添加/删除项目，然后 返回被删除的项目。

  arrayObject.splice(index,howmany,item1,.....,itemX)

  index	规定添加/删除项目的位置，使用负数可从数组结尾处规定位置。

  howmany	要删除的项目数量。如果设置为 0，则不会删除项目。

  item1, ..., itemX	可选。向数组添加的新项目。

  arr1.splice(1,1,6,7);//删除第二个数，并且添加６，７

- // join() 方法用于把数组中的所有元素放入一个字符串。

  var d = arr.join();
   打印输出　0,0,1,2,3,a,b,c,1,2,3

- toString() 方法可把数组转换为字符串，并返回结果。

  arrayObject 的字符串表示。返回值与没有参数的 join() 方法返回的字符串相同。
- sort() 方法用于对数组的元素进行排序。
按字母顺序排序

```js
<script type="text/javascript">

var arr = new Array(6)
arr[0] = "George"
arr[1] = "John"
arr[2] = "Thomas"
arr[3] = "James"
arr[4] = "Adrew"
arr[5] = "Martin"

document.write(arr + "<br />")
document.write(arr.sort())

</script>
```
输出：
George,John,Thomas,James,Adrew,Martin
Adrew,George,James,John,Martin,Thomas

数字排序(仅能按首位大小排序)
  ```js
   var arr = [1,5,7,2,6,77,8];
      arr.sort();//注：按首位排序
      console.log(arr);
  ```
若想按大小排序，需要一个函数进行排序
```js
     function count(a,b) {
       return a-b
     }
     var arr1 = [1,56,78,3,121];
     arr1.sort(count)
     console.log(arr1);
```
数组循环：
var arr = [1,"aa",2,"bb",3,"cc"];
for(var i in arr){
  console.log(arr[i])
}

### 数学对象
1. 取随机数
```js
var num = parseInt(Math.random()*10);//0~10的随机整数
```
2. 向上取整(进１)
```js
var num = Math.ceil(3.14); //向上取整
```
3. 向下取整
```js
var num２ = Math.floor(3.14); //向下取整
```
4.四舍五入
```js
var num３ = Math.round(3.14); //四舍五入
```
#### 随机抽奖实例(随机)：
```js
var arr = new Array("zhangsan","zhaosi","wangwu","sansn");
//<input type="button" name="name" value="抽奖">写在body 里

  $(":button").click(function () {
    var n = arr.length;
    var num = Math.floor(Math.random()*n);
    if (n==0) {
      console.log("抽奖完成");
    }else {
      console.log(arr[num]);
      arr.splice(num,1);//将抽过的人从数组中删掉
    }

    console.log(arr);
  })
```
#### 有概率抽奖实例
```js
$(":button").click(function(){
  var arr1 = ["一等奖","二等奖","三等奖","谢谢参与"];
  var num = Math.ceil(Math.random()*10);

  if (num == 1) {
    console.log(arr1[0]);//仅抽到１的时候为一等奖

  }else if(num <=3 && num>1){
    console.log(arr1[1]);


  }else if (num>3 && num<=8) {
    console.log(arr1[2]);


  }else {
    console.log(arr1[3]);


  }

})
```

### 日期
- getTime() 方法可返回距 1970 年 1 月 1 日之间的毫秒数。
- getYear()	请使用 getFullYear() 方法代替。
- getHours()	返回 Date 对象的小时 (0 ~ 23)。
- getMinutes()	返回 Date 对象的分钟 (0 ~ 59)。
- getSeconds()	返回 Date 对象的秒数 (0 ~ 59)。

```js
function getTime() {
  var date = new Date();
  var hour = date.getHours();
  var minute = date.getMinutes();
  var second = date.getSeconds();
  var str = hour + ":" +minute + ":" + second;
  $(":text").val(str);//将时间放到文本中
}

getTime();
setInterval(getTime,1000)
//setInterval(函数名,毫秒数)
//每秒执行一次
```
### 倒计时实例
```js
function getTime() {
  var date = new Date();

 var Hour = 15;
 var Minute = 41;
 var Second = 22;

 var hour = date.getHours();
 var minute = date.getMinutes();
 var second = date.getSeconds();

 var showH = Hour - hour;
 var showM = Minute - minute;
 var showS = Second - second;
 // console.log("剩余时间"+ show);
 if (showS<0) {
   showM-=1;
   showS = showS + 60;
 }
 if (showM<0) {
   showS-=1;
   showM = showM + 60;
 }
 if (showH<10) {
   showH = "0" +showH;
 }
 if (showM<10) {
   showM = "0" +showM;
 }
 if (showS<10) {
   showS = "0" +showS;
 }
 if (showS == 0 && showM == 0 && showH == 0) {
   console.log("抽奖结束");
   clearInterval(t)
 }
 var show = showH + ":"+showM + ":" +showS;

  $(":text").val("抽奖倒计时："+show);
}
   getTime();
    var t = setInterval(getTime,1000);
//遇到问题，关于借位的问题
```
### 计算两个数字的乘积，并返回结果：

```js
function myFunction(a,b)
{
return a*b;
}

document.getElementById("demo").innerHTML=myFunction(4,3);
```
"demo" 元素的 innerHTML 将是：
12

### 返回字符串的长度
```js
<script type="text/javascript">

var txt="Hello World!"
document.write(txt.length)

</script>
```
### 为字符串添加样式
```js
<script type="text/javascript">

var txt="Hello World!"

document.write("<p>Big: " + txt.big() + "</p>")
document.write("<p>Small: " + txt.small() + "</p>")

document.write("<p>Bold: " + txt.bold() + "</p>")
document.write("<p>Italic: " + txt.italics() + "</p>")

document.write("<p>Blink: " + txt.blink() + " (does not work in IE)</p>")
document.write("<p>Fixed: " + txt.fixed() + "</p>")
document.write("<p>Strike: " + txt.strike() + "</p>")

document.write("<p>Fontcolor: " + txt.fontcolor("Red") + "</p>")
document.write("<p>Fontsize: " + txt.fontsize(16) + "</p>")

document.write("<p>Lowercase: " + txt.toLowerCase() + "</p>")
document.write("<p>Uppercase: " + txt.toUpperCase() + "</p>")

document.write("<p>Subscript: " + txt.sub() + "</p>")
document.write("<p>Superscript: " + txt.sup() + "</p>")

document.write("<p>Link: " + txt.link("http://www.w3school.com.cn") + "</p>")
</script>
```

#　dom 节点
　　文本节点　属性节点　元素节点

### Document 对象方法
方法	描述
- close()	关闭用 document.open() 方法打开的输出流，并显示选定的数据。
- getElementById()	返回对拥有指定 id 的第一个对象的引用。
- getElementsByName()	返回带有指定名称的对象集合。
- getElementsByTagName()	返回带有指定标签名的对象集合。
- open()	打开一个流，以收集来自任何 document.write() 或 document.writeln() 方法的输出。
- write()	向文档写 HTML 表达式 或 JavaScript 代码。
- writeln()	等同于 write() 方法，不同的是在每个表达式之后写一个换行符。
### 设置属性

```js
var oA = document.getElementById('btn')
var oA1 = document.getElementsByTagName('a');//数组形式

oA1[1].onmouseenter = function () {
  this.setAttribute("herf","document.html")//设置属性
  var herf = oA1[0].getAttribute("herf") //获取属性
```

- innerHTML 获取原生dom对象里面的所有内容（包括标签）或者设置里面的所有内容
- dom对象 获取和设置样式 .style    (获取的时候只能获取行内样式)
- className 获取和设置dom对象的 class名
### 图片切换
```js
function G(sId){
  return document.getElementById(sId)
}
var oA = document.getElementsByTagName('a');

for(var i = 0 ;i < oA.length;i++){
  oA[i].index = i;

  var arr = oA[i].className.split(" ");
  for(var m = 0;m<arr.length;m++){
    if(arr[m] == "active"){
      arr.splice(m,1);
    }
  }
  var str = arr.join(" ");
  oA[i].cla = str;
  oA[i].onclick = function(event){
    var marginL = this.index * -400 + "px";
    G("pic").style.marginLeft = marginL;
    event.preventDefault();
    for(var j =0;j<oA.length;j++){
      
      //  oA[j].style.backgroundColor = "white"
      //  oA[j].style.color = "black"
      oA[j].className = oA[j].cla;
    }
    // this.style.backgroundColor = "red"
    // this.style.color = "blue"
    this.className = this.cla + " " + "active";
  }
}

var str = "aa active a3";
var arr = str.split(" ");//["aa","active","a3"]
console.log(arr)
for(var i = 0;i<arr.length; i++){
  if(arr[i] == "active"){
    arr.splice(i,1)
  }
}
var str1 = arr.join(" ");
console.log(str1)

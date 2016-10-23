###　dom 节点
　　文本节点　属性节点　元素节点

#### Document 对象方法
方法	描述
- close()	关闭用 document.open() 方法打开的输出流，并显示选定的数据。
- getElementById()	返回对拥有指定 id 的第一个对象的引用。
- getElementsByName()	返回带有指定名称的对象集合。
- getElementsByTagName()	返回带有指定标签名的对象集合。
- open()	打开一个流，以收集来自任何 document.write() 或 document.writeln() 方法的输出。
- write()	向文档写 HTML 表达式 或 JavaScript 代码。
- writeln()	等同于 write() 方法，不同的是在每个表达式之后写一个换行符。
##### 设置属性
```js
var oA = document.getElementById('btn')
var oA1 = document.getElementsByTagName('a');//数组形式

oA1[1].onmouseenter = function () {
  this.setAttribute("herf","document.html")//设置属性
  var herf = oA1[0].getAttribute("herf") //获取属性
```

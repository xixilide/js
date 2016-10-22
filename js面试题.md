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

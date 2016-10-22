# window对象
//BOM 浏览器对象模型
```js
var a = 10;
console.log(window.a);
function fun() {
  console.log(a);
}
window.fun() //相当于fun()
//window对象下的方法
var obj = {
  name　:"hang",
  sayName:function () {
    console.log(this.name);
  }
}
```
### window对象下的方法
- console.log
- alert
- setInterval 设定一个时间间隔后(第二个参数)，反复执行“代码字符表达式”的内容
- clearInterval
- setTimeout  定时设置，当到了指定的毫秒数后，自动执行代码字符表达式。
- clearTimeout  取消以前的定时设置，其中的参数是用setTimeout设置时的返回值。
- open  返回的是该窗口的引用。
- close  方法用于自动关闭浏览器窗口。
- confirm
- prompt
    window.prompt(提示字符串，缺省文本)

    功能：显示一个输入框，在输入框内显示提示字符串，在输入文本框显示缺省文

    本，并等待用户输入，当用户单击“确定”按钮时，返回用户输入的字符串，当

    单击“取消”按钮时，返回null值。
- moveBy
- moveTo  将窗口移动到指定的指定坐标(x,y)处
- resizeBy
- resizeTo
- scrollBy　window.scrollBy(水平位移量，垂直位移量)

功能：将窗口中的内容按给定的位移量滚动。参数为正数时，正向滚动，否则反

向滚动。
- scrollTo　
window.scrollTo(x,y)

功能：将窗口中的内容滚动到指定位置。
- find
window.find()

功能：当触发该方法时，将弹出一个“find”(查找)对话窗口，并允许用户在触

发find方法的页面中查找一个字符串。
- back
- forward
- home
- stop
- print
- blur
- focus
- captureEvent
- enableExternalCapture
- disableExternalCapture
- handleEvent
- releaseEvent
- routeEvent
- scroll
#### Location 对象

Location 对象包含有关当前 URL 的信息。

Location 对象是 Window 对象的一个部分，可通过 window.location 属性来访问。

- reload()	重新加载当前文档。location.reload(force)
- replace()	用新的文档替换当前文档。location.replace(newURL) 没有历史记录，不能回退
```js
console.log(location.url);//返回url #后面的
console.log(location.host);//返回完整的url 路径
console.log(location.herf);//	设置或返回完整的 URL
console.log(location.hash);//设置或返回从井号 (#) 开始的 URL（锚）
console.log(location.port);//设置或返回当前 URL 的端口号。
$(":button").click(function () {
  location.assign("http://baidu.com")//	加载新的文档。

})
```
### History 对象
History 对象包含用户（在浏览器窗口中）访问过的 URL。
History 对象是 window 对象的一部分，可通过 window.history 属性对其进行访问。

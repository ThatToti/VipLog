# js技巧库

 ![{2192BB9D-AF74-4CCF-A0FD-0FA67B74C7F7}](C:\Users\Administrator\Desktop\{2192BB9D-AF74-4CCF-A0FD-0FA67B74C7F7}.png)

**1.获取dom元素不再使用dom获取操作，会比较耗性能**

推荐使用：querySelector（），querySelectorAll（）两个方法

```js
var body=document.querySelector('body');
//就是取得body元素

var div=document.querySelector('#id');
//取得id为id的元素的第一个

var img=document.querySelector('img.selector');
//取得类为selector的img的第一个元素
```

```js
var uls=document.querySelectorAll("ul");
//取得所有dom中所有的ul，取具体某一个要uls[i];

var strongs=document.querySelectorAll("p strong");
//取得所有p元素中的strong元素
```

>  **重点技巧** 

```js
var $=document.querySelector.bind(document);
//直接取所有dom元素

$("#list");
$(".class");
$("ul");
//分别的意思是取id为list的，class为class的，tag为ul的，十分方便，其实就是参考了jq的方法。
```

**2.函数库里化**

```js
function curry(fn){
	var args=Array.prototype.slice.call(arguments,1);
  	return function(){
  	  var innerArgs=Array.prototype.slice.call(arguments);
      var finalArgs=args.concat(innerArgs);
      return fn.apply(null,finalArgs);
  	};
}
```


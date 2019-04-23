# 预解析

``` javascript
foo();
function foo(){
	return bar();
	var bar = function(){return 8}
	function bar(){return 9}
}
```
关于预解析的理解还不够透彻 本以为是8但结果是9 关键就在这个return

如果是不加return 那么理解的没有错误

``` javascript

foo();
function foo(){
	
	var bar = function(){return 8}
	function bar(){return 9}
	return bar();
}

```
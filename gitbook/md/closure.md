# 关于闭包的问题

``` javascript
var a = 5;
function foo(){
	var a = 9;
	return function(){
		a = 7;
	}
}
foo()();

console.log(a);
```

那么a的话肯定是个5
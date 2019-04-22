# 关于宏任务和微任务

``` javascript
setTimeout(function(){
	console.log("setTimeout")
},0)

new Promise(function(resolve,reject){
	resolve("resolve");
	console.log("promise");
}).then(function(success){
	console.log(success);
})

console.log("start")
```
执行顺序为

promise
start
resolve
setTimeout
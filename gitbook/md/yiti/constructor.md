https://github.com/Advanced-Frontend/Daily-Interview-Question

``` javascript
function Foo(){
    Foo.a = function() {
        console.log(1)
    }
    this.a = function(){
        console.log(2)
    }
}
Foo.prototype.a = function(){
    console.log(3)
}
Foo.a = function(){
    console.log(4)
}
Foo.a();
let obj = new Foo();
obj.a();
Foo.a();
```

我觉得的结果是
首先调用的是静态方法
4
其次实例化了构造函数 重写静态方法 定义成员方法
2
1

蒙对了
我觉得这个题考察的是原型链 如果对象中找不到则从原型链上找

# 

``` javascript
function changeObjProperty(o){
    o.siteUrl = "http://www.baidu.com";

    o = new Object();
    o.siteUrl = "http://www.google.com";
}
var webSite = new Object();

changeObjProperty(webSite);
console.log(webSite.siteUrl);

```

我觉得的结果是
函数的参数是按值传递

"http://www.baidu.com"


ECMAScript中所有函数的参数都是按值传递的。

也就是说，把函数外部的值复制给函数内部的参数，就和把值从一个变量复制到另一个变量一样。基本类型的传递如同基本类型的复制一样，而引用类型值的传递，如同引用类型变量的复制一样。

``` javascript
['1', '2', '3'].map(parseInt)
```

api

``` javascript
parseInt(string[, radix]);

arr.map(function callback(currentValue[,index[, array]]) {
 // Return element for new_array
 }[, thisArg])
```

实际执行
``` javascript
['1', '2', '3'].map((item, index) => {
	return parseInt(item, index)
})
```

``` javascript
async function async1() {
    console.log('async1 start');
    await async2();
    console.log('async1 end');
}
async function async2() {
    console.log('async2');
}
console.log('script start');
setTimeout(function() {
    console.log('setTimeout');
}, 0)
async1();
new Promise(function(resolve) {
    console.log('promise1');
    resolve();
}).then(function() {
    console.log('promise2');
});
console.log('script end');

```
从调用开始看

script start

async1 start

async2

promise1

script end

async1 end

promise2

setTimeout

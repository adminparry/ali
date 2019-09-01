# 从一个题目引出一个数组骚操作

## 下面代码中 a 在什么情况下会打印 1

``` javascript

var a = ?;
if(a == 1 && a == 2 && a == 3){
 	console.log(1);
}
```

直接想到的做法是重写toString 或者是valueOf方法 然后自定义返回的值就可以了

比如这样

``` javascript

let a = {
  i: 1,
  valueOf () {
    return a.i++
  }
}

if(a == 1 && a == 2 && a == 3) {
  console.log(1);
}

```

但是我看到了比较骚的做法分享一下

``` javascript
var a = [1,2,3];	
a.join = a.shift;
if(a == 1 && a == 2 && a == 3) {
  console.log(1);
}
```


从这段代码中引起我无数的深思 我觉得我该吃饭去了

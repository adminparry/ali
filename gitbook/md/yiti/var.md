# 变量提升

``` javascript
var name = 'Tom';
(function() {
    if( typeof name == 'undefined'){
        var name = 'Jack';
        console.log('Goodbye %s', name);
    } else {
        console.log('Hello %s', name);
    }
})()
```
## 结果
``` javascript
Goodbye Jack
```
## 
``` javascript
var name = 'Tom';
(function() {
    var name;
    if( typeof name == 'undefined'){
        name = 'Jack';
        console.log('Goodbye %s', name);
    } else {
        console.log('Hello %s', name);
    }
})()
```
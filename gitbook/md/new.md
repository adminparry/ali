# new的实现

``` javascript
Function.prototype.instance = function(){
    let constructor = Array.prototype.shift.call(this, arguments);
    let args = arguments;
    const ret = new Object();
    ret.__proto__ = constructor.prototype;
    constructor.call(obj, ...args);
    return ret;
}
```
# 属性访问

``` javascript

var obj = {a:{b:c{d:23}},b:12,c:9}
get(obj, 'a.b.c.d')
<!-- 23 -->
obj = {};

get(obj, 'a.b.c.d')
<!-- undefined -->
get(obj, 'a.b.c.d', "shuidi")
<!-- 如果不存在 给定默认值shuidi -->


```

## 脑子中想到的最简单的做法就是使用with然后进行解析

``` javascript
function get(obj, path, defaultVal){

	with(obj){
		try{
			return eval(path)
		}catch(e){
			return defaultVal
		}
		
	}
}

```
## 当然面试官好像不让我这么做

那换种方式也可以那就用循环来实现被

``` javascript

function get(obj, path, defaultVal){
	var pathList = path.split("."),
		len = pathList.length,
		index = 0,
		ret = obj[pathList[index]];
	
	while(ret && index < len - 1){
		
			index++
			ret = ret[pathList[index]];
	
		
	}

	return ret || defaultVal;
}

```
心里明明知道使用递归的方式更简单一点 但是自己喜欢while 所以在纸上写了 但是面试的时候在纸上好像写错了 手残党没有办法 len忘记写了

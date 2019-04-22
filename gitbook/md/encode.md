# 关于解码问题

水滴互助

题目

从一个未知被编码多少次的url解出最原始的url

例如 "https://www.baidu.com/?wd=%252525E6%25252588%25252591%252525E6%25252598%252525AF"

我的印象中是被编码多少次都是一样的 可实际上确实不是 说明人的印象是不准确的 然而脑子中还飘过一个%25

但是我面试的时候仍然是按照印象来答的 回来的时候顺便看了下

``` javascript
var url = "https://www.baidu.com/?wd=%252525E6%25252588%25252591%252525E6%25252598%252525AF";

function decode(str){
	if(str.indexOf("%25") > -1){
		return decode(decodeURI(str))
	}

	return decodeURI(str);
}

console.log(decode(url))
```
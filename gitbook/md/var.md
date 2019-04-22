# 一个很老的问题

循环中加点击事件的问题

``` html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	<ul id="ul">
		<li>1</li>
		<li>2</li>
		<li>3</li>
		<li>4</li>
	</ul>			
</body>
<script>
	var ul = document.getElementById("ul");
	for (let i = 0; i < ul.children.length; i++) {
		ul.children[i].onclick = function(){
			alert(i);
		}
	};
</script>
</html>
```
现在有let块级作用域了所以也不用像之前添加个属性那么处理了

添加属性的处理

``` html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	<ul id="ul">
		<li>1</li>
		<li>2</li>
		<li>3</li>
		<li>4</li>
	</ul>			
</body>
<script>
	var ul = document.getElementById("ul");
	for (var i = 0; i < ul.children.length; i++) {
		ul.children[i].index = i;
		ul.children[i].onclick = function(){
			alert(this.index);
		}
	};
</script>
</html>
```
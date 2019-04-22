# box-sizing

问红色的块的宽高是多少

注意是红色 呵呵 我就忘记了

``` html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		.box{
			width: 200px;height: 200px;
			background: red;
			border: 20px solid black;
			margin: 20px;
			padding: 20px;
			box-sizing:border-box;
		}
	</style>
</head>
<body>
	<div class="box"></div>
</body>
</html>

```

(200 - 20\*2) \* (200 - 20\*2) = 160\*160
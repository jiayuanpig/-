JQuery

- jQuery是一个JavaScript函数库。
- jQuery是一个轻量级的"写的少，做的多"的JavaScript库。

# jQuery解决的问题

1、浏览器兼容问题
2、代码简洁：代码量少，不乱
3、实现动画效果
4、代码容错性
5、window.onload事件避免覆盖


# Jquery版本
- 普通版本
- min：它是压缩过的版本

区别：我们开发过程中，会用未压缩的版本，或者压缩的。项目上线的时候，我们要用压缩过的版本。


# Jquery引用
- 方式一:本地引用
```html
	<script src="js/jquery-1.11.1.js"></script>
```
- 方式二:CDN(内容分发网络)在线使用
```html
	<!-- 不大推荐使用Google CDN来获取版本，因为Google产品在中国很不稳定 -->
	<head>
		<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.10.2/jquery.min.js">
		</script>
	</head>

```

多库引用:

同一个页面，引入包含$变量的其他js库，保证它们不发生命名冲突。
```html
	// other_lib.js 包含$
	<script src="other_lib.js"></script>
	<script src="jquery-1.11.1.js"></script>
	<script>
		$.noConflict();
		// 可以使用其他库的$符号了
		// 使用jQuery
		jQuery(document).ready(function(){});
	</script>
```


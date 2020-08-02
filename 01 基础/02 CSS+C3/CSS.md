CSS:层叠样式表

# 容器
<span>
容器标签,不具备任何特殊功能,仅当容器使用,用于包裹文本,便于给文本增加样式

<div>
容器标签,不具备任何特殊功能,仅当容器使用.可以包裹任何内容,也可以相互包裹
空的div:默认宽度100%,高度0

# 浏览器默认设置
字体大小:16px
行高:21px

# CSS选择器
ID选择器(唯一):			#idName
类选择器(可以多次使用):	.className
标签选择器:				labelName
通配符选择器:				*

# 页面实现
导航栏的分隔:

	方法一:使用span来添加分隔
	
	```
		<a><a/>
		<span>|<span/>
		<a><a/>
		<span>|<span/>
		<a><a/>
	```
	
	方法二:定义a标签的样式,只留下右边框(样式略),最后一个选项单独设置样式无边框
	
	```
		<a class="item"><a/>
		<a class="item"><a/>
		<a class="item" style="border:none"><a/>
	```

# 样式优先级
	行内样式>ID选择器>类选择器>标签选择器>通用选择器
权重:	1000	100		10		1			0

注:如果使用多级选择器,权重相加比较

# CSS文本属性
* 颜色：color
* 字体:font-family
* 行高:line-height
* 大小:font-size
* 加粗:font-weight
* 倾斜:font-style
* 首行缩进:font-indent
* 水平对齐:text-align
* 文字修饰:text-direction

# CSS背景图片设置
```
	#img{
		background-image:url(img/dog.gif);<!-- 背景图片地址 -->
		background-repeat:no-repeat;<!-- 图片是否重复 -->
		background-position:right buttom;<!-- 图片位置为右下方 -->
		background-attachment:scroll/fixed; <!-- 背景图片是固定还是滚动 -->
	}
```
要想引用背景图片的不同部分,可以采用 background-position: -10px -10px; 来进行调整


# 浮动
浮动元素会脱离文档，与其他元素发生重叠

浮动元素**不会与文字/图片/表单发生重叠**，就可以做出文字环绕的效果

浮动元素无法撑开父元素

清除浮动影响：
1. overflow:auto
2. clear:left/right/both(不受左浮动/右浮动/所有的影响)

浮动元素只参考前一个元素的影响

# 盒子模型
- margin:外边距
- padding:内边距
- border:边框

盒子总共四个方向:top right bottom left

margin:auto;可以使得该元素居中显示(只有水平方向有效)

margin不会改变元素大小，padding填充，会改变元素大小

# CSS属性简写
background：背景颜色 背景图片 是否重复
- background:gray url(img/XXX) no-repeat;
- background:url(img/XXX) repeat-y;
- background:gray;

border：边框粗细 边框类型 边框颜色
- border:1px solid #ccc;
- border:1px solid;(只有颜色可以省略，颜色默认黑色)

font:斜体 加粗 字号/行高 字体(包含备用字体) 
- font:italic bold 20px/35px arial,"微软雅黑"；

(可以省略一些,但是要注意顺序问题)

margin/padding: 上 右 下 左
- 上 左右 下
- 上下 左右
- 上下左右

color
- 名称
- rgb(255,255,255);
- #FFFFFF;
- rgba(255,255,255,0.5) (a:透明度)




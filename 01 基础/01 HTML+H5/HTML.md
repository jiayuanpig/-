HTML:超文本标记语言

# 标签属性
```
<a href="" target=""/>
```
- href:表示链接跳转地址
- target:表示是否在新的窗口打开新页面 (_blank:新窗口打开)

```
<img src="" title="" alt=""/>
```
- src:表示图片路径
- title:表示鼠标滑上去的提示
- alt:表示图片加载失败的文字

```
<table/>
	<tr>表示一行
	<td>表示一个格
	<col>表示一列,可以在col中设置属性来调整表格列的宽度
	<th>表示加粗并水平居中的<td>
	<colgroup span="6" width="100px">:对前6列一起设置属性
```
- colspan:表示横向单元格合并
- rowspan:表示纵向单元格合并
- cellspacing:表示单元格空隙
- align:排列,在<td></td>中表示对齐方式

```
<form action="">
```
- action:提交地址

```
<input type="" name=""/>
```
- type:
	text/password/button/radio/checkbox/file
	submit/reset
- name:提交的数据必须有该属性

注:input必须放在form标签内才能生效
```
<input type="button" value=""/>
```
- value:表示按钮里面的文字

# 不能互相嵌套的标签
```
<a> <p> <h1>...<h6>
```

# form的两种方式 method="post/get"
- post:提交数据,地址栏没有显示
- get:获取数据,地址栏会携带数据

注:get请求不能提交大量数据,但是post可以,尽量不要混用



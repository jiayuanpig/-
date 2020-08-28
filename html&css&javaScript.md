# 常用html&css&javaScript


### 表单
``` javaScript
	* 表单：
		* 概念：用于采集用户输入的数据的。用于和服务器进行交互。
		* form：用于定义表单的。可以定义一个范围，范围代表采集用户数据的范围
	        * 属性：
	            * action：指定提交数据的URL
	            * method:指定提交方式
	        * 表单项中的数据要想被提交：必须指定其name属性


		* 表单项标签：
			* input：可以通过type属性值，改变元素展示的样式
				* type属性：
					* text：文本输入框，默认值
						* placeholder：指定输入框的提示信息，当输入框的内容发生变化，会自动清空提示信息	
					* password：密码输入框
					* radio:单选框
						* 注意：
							1. 要想让多个单选框实现单选的效果，则多个单选框的name属性值必须一样。
							2. 一般会给每一个单选框提供value属性，指定其被选中后提交的值
							3. checked属性，可以指定默认值
					* checkbox：复选框
						* 注意：
							1. 一般会给每一个单选框提供value属性，指定其被选中后提交的值
							2. checked属性，可以指定默认值


					* file：文件选择框
					* hidden：隐藏域，用于提交一些信息。
					* 按钮：
						* submit：提交按钮。可以提交表单
						* button：普通按钮
						* image：图片提交按钮
							* src属性指定图片的路径	
	
			   * label：指定输入项的文字描述信息
				   * 注意：
					   * label的for属性一般会和 input 的 id属性值 对应。如果对应了，则点击label区域，会让input输入框获取焦点。
			* select: 下拉列表
				* 子元素：option，指定列表项
				
			* textarea：文本域
				* cols：指定列数，每一行有多少个字符
				* rows：默认多少行。
```
### css

```javaScript
			1. 字体、文本
				* font-size：字体大小
				* color：文本颜色
				* text-align：对其方式
				* line-height：行高 
			2. 背景
				* background：
			3. 边框
				* border：设置边框，符合属性
			4. 尺寸
				* width：宽度
				* height：高度
			5. 盒子模型：控制布局
				* margin：外边距
				* padding：内边距
					* 默认情况下内边距会影响整个盒子的大小
					* box-sizing: border-box;  设置盒子的属性，让width和height就是最终盒子的大小				*float：浮动
	                * left
	                * right
	            
```

### js事件
```javascript
1. 点击事件：
		1. onclick：单击事件
		2. ondblclick：双击事件
	2. 焦点事件
		1. onblur：失去焦点
		2. onfocus:元素获得焦点。

	3. 加载事件：
		1. onload：一张页面或一幅图像完成加载。

	4. 鼠标事件：
		1. onmousedown	鼠标按钮被按下。
		2. onmouseup	鼠标按键被松开。
		3. onmousemove	鼠标被移动。
		4. onmouseover	鼠标移到某元素之上。
		5. onmouseout	鼠标从某元素移开。
		
		5. 键盘事件：
		1. onkeydown	某个键盘按键被按下。	
		2. onkeyup		某个键盘按键被松开。
		3. onkeypress	某个键盘按键被按下并松开。

	6. 选择和改变
		1. onchange	域的内容被改变。
		2. onselect	文本被选中。

	7. 表单事件：
		1. onsubmit	确认按钮被点击。
		2. onreset	重置按钮被点击。

```

### DOM模型
```javascript
 核心DOM模型：
	* Document：文档对象
		1. 创建(获取)：在html dom模型中可以使用window对象来获取
			1. window.document
			2. document
		2. 方法：
			1. 获取Element对象：
				1. getElementById()	： 根据id属性值获取元素对象。id属性值一般唯一
				2. getElementsByTagName()：根据元素名称获取元素对象们。返回值是一个数组
				3. getElementsByClassName():根据Class属性值获取元素对象们。返回值是一个数组
				4. getElementsByName(): 根据name属性值获取元素对象们。返回值是一个数组
			2. 创建其他DOM对象：
				createAttribute(name)
            	createComment()
            	createElement()
            	createTextNode()
		3. 属性
	* Element：元素对象
		1. 获取/创建：通过document来获取和创建
		2. 方法：
			1. removeAttribute()：删除属性
			2. setAttribute()：设置属性
	* Node：节点对象，其他5个的父对象
		* 特点：所有dom对象都可以被认为是一个节点
		* 方法：
			* CRUD dom树：
				* appendChild()：向节点的子节点列表的结尾添加新的子节点。
				* removeChild()	：删除（并返回）当前节点的指定子节点。
				* replaceChild()：用新节点替换一个子节点。
		* 属性：
			* parentNode 返回节点的父节点。
```


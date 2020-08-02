ECMA5:JavaScript通用标准

# 严格模式 "use strict"
在严格模式下,浏览器对JS的要求更加苛刻

- 如果在变量赋值时,没有使用var进行声明,就当作全局变量进行处理
- 在 "use strict"模式下会报错
- "use strict":写在哪个作用域下,该作用域以下所有代码遵从严格模式
- 不要轻易在全局范围开头增加 "use strict"

添加的函数

- 数组.indexOf(查找内容):寻找括号内内容在数组中的位置
- 数组.forEach(function(item,index,array){}):遍历数组
- 数组.map(function(item,index,array){}):映射 遍历-->操作-->返回
- 数组.reduce(function(pre,next,index,array){}):归并
- 数组.filter(function(item,index,array){}):过滤
- 数组.some(function(item,index,array){}):
	- 判断return后面的条件是否成立,返回boolean值
	- 如果匹配成功,返回true,后面就不再进行遍历
- 数组.every(function(item,index,array){}):
	- 和some类似,但是要求每一项都符合要求,才能返回true
	- 如果匹配不成功,返回false,后面就不再进行遍历


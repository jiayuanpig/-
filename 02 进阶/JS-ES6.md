ES6:最新JS标准

# let的使用

let用来声明变量,和var 类似,但是其声明的变量只在let命令所在的代码块内有效

- 存在块级作用域(用于区分全局和块级变量)
- 不存在声明提升(先声明,后使用,不能颠倒)
- 不允许重复声明(包括普通变量和函数参数)

const的使用
- 声明常量,不要试图改变常量的值,其他语法参照let

# 解构赋值
按照一定的模式,从数组和对象中提取值,对变量进行赋值

数组:
```js
	let [a,b,c] = [1,2,3]
	//对a,b,c分别进行赋值,结果为1,2,3
	console.log(a,b,c);

	let [a = 3,b] = [2]
	// a重新赋值,b未赋值,结果为2,undefined
	console.log(a,b);

	let c;
	let [a = 2] = [c];
	//a仍为2,不会被c的undefined覆盖

```

对象:
```js
	let{a,b} = {a:"aaa",b:"bbb"};//a:aaa b:bbb
	let{a:b} = {a:"aaa"};// a:undefined b:aaa
	let{a,b = 5} = {a:1};//a:1 b:5
```

# 模板字符串

将变量和表达式直接嵌入字符串

使用反引号(``)拼接多行字符串

```js
	//ES5
	// var obj = {"name":"John","age":20};
	// var name = obj.name;
	// var age = obj.age;
	// console.log(name + "年龄是" + age);
	//ES6:不允许重复定义变量
	let obj = {"name":"John","age":20};
	let {name,age} = obj;
	console.log(`${name}年龄是${age}`);//不能使用双引号
```

# 箭头函数
- 表示方法
	- let f = () => 1;
	- 等价于 var f = function(){return 1;}
	- 例子:
	```
		let f = (a) =>{
			let b = 10;
			return a + b;
		}
	```	
		
- this指向:定义时所在的作用域,不是执行时所在的作用域

# 新的数据结构

## set结构

构造函数及遍历
```js
	//构造函数:值不能重复
	let set = new Set([1,2,3,4,4])
	//所以实际结果中只有1,2,3,4
	//扩展运算符...:将set转换为数组
	let arr = [...set];
	
	//set的遍历
	//以下结果一样
	for(let i of set){
		console.log(i);
	}
	for(let i of arr){
		console.log(i);
	}
```

- 属性
	- set.size
- 方法
	- set.add(n):添加某元素
	- set.delete(n):删除某元素
	- set.has(n):是否含有某元素
	- set.clear():清空
- 其他方法
	- keys():返回键名的遍历器
	- values():返回键值的遍历器
	- entries():返回键值对的遍历器
	- forEach():使用回调函数遍历每个成员

验证:
```js
	var set = new Set([2,5,6,3,4])
	for(let item of set.keys()){
		// console.log(item);
		//2 5 6 3 4
	}
	for(let item of set.values()){
		// console.log(item);
		//2 5 6 3 4
	}
	for(let [key,item] of set.entries()){
		// console.log(item);
		//2 5 6 3 4
	}
	set.forEach((item,key) => console.log(item,key))
	//2 2 5 5 6 6 3 3 4 4
```

## map结构
```js
	let map = new Map([["name","John"],["age",30]]);
	//通过set方法增加map中的内容
	map.set("sexy","male");
```

方法同set结构

# 生成器函数(generator)

```js
	function* foo(x){
		yield x + 1;
		yield x + 2;
		return x + 3;
	}
	var f = foo(1);
	console.log(f.next(),f.next(),f.next());
	// 2,3,4
```

- yield:暂停当前函数
- f.next():调出输出的值

```js
	function* foo(x){
		var y = 2*(yield(x+1));
		var z = yield(y/3);
		return (x+y+z)
	}
	var f = foo(5);
	//next():参数表示上一次的返回值
	console.log(f.next());
	console.log(f.next(12));
	console.log(f.next(13));
	//返回:6,8,42
	// 6 = 5 + 1
	// 8 = 2*12/3 
	// 42 = 5 + 24 + 13
```

例子:生成斐波那契数列

```js
	// 生成斐波那契数列
	function* feiBo(n){
		let a = 0;
		let b = 1;
		for(let i = 0; i < n; i++){
			yield a;
			let temp = a + b;
			a = b;
			b = temp;
		}
	}
	
	var f = feiBo(6);
	for(let i of f){
		console.log(i);
		//0,1,1,2,3,5
	}
```

# 类(class)
```js
	class Person{
		constructor(name){
			this.name = name;
		}
		sayHello(){
			console.log(this.name);
		}
	}
	var p = new Person();
	console.log(p.name);//undefined
	var p2 = new Person("John");
	console.log(p.name);//John
	
```


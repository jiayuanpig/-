# Javascript
Javascript
这是我学习JavaScript的文件

## **第一章：值，类型，运算符**
### 1.1 基本值类型
   * 数字
   * 字符串
   * 布尔值
   * 对象
   * 函数
   * 未定义类型
### 1.2 特殊数字
    Infinity    正无穷
    -Infinity   负无穷
    NaN         非数值
### 1.3 布尔值
   *  字符串比较是按照字母顺序来进行比较的
       - 大写字母小于小写字母
   *  NaN表示非法运算结果
   *  undefind和null可以近似看作可互换的值
   *  0、空字符串、NaN被JS看作相等
### 1.4 逻辑运算符的短路特性
   *  **||**  当左侧值为true时，后面不执行，直接返回左侧值
   *  **&&**  当左侧值为false时，后面不执行，直接返回左侧值

## **第二章：程序结构**
### 2.1 关键字和保留字
    break 
    case catch continue 
    debugger default delete do
    else
    false finally for function
    if implements in instanceof interface 
    let
    new null 
    package private protected public
    return
    static switch
    throw true try typeof this
    var void 
    while with
    yeild
    无需一定要记住，当定义的变量无法实现要求时，可以考虑这方面原因
### 2.2 窗口函数
   * alert()：弹出一个弹窗，只能确认
   * confirm()：当用户选择“是”，返回true；选择“否”，返回false
   * prompt(string1,string2):string1表示问题，string2表示文本框默认值。函数可以返回文本框的值

## **第三章：函数** 
### 3.1 函数声明
1. var fun = function(){};
2. function fun(){};
### 3.2 函数调用
    函数声明会被移动到其作用域的顶端，所以在函数的作用域内，无论写在哪里都可以运行
### 3.3 函数可选参数
* JS对传入的参数数量几乎不做任何限制，多余的参数会被浏览器忽略
* 当存在参数不足的问题，我们可以对参数设置一个默认值

 ```参数实例：
    function power(base,exponent){
        if(exponent == null)
            exponent = 2;
        var result = 1;
        for(var count = 0;count<exponent;count++){
            result *= base
        }
        return result;
    }
    consolo.log(power(4));
 ```
### 3.4 闭包
* 闭包：引用特定的局部变量实例的功能
* 优点：不用考虑局部变量的生命周期
```闭包实例：
    //wrapValue和wrapValue2有什么区别吗？
        function wrapValue(n) {
            var localVariable = n;
            return function () {
                return localVariable;
            };
        }
        var wrap = wrapValue(2);
        console.log(wrap());

        function wrapValue2(n) {
            var localVariable = n;
            return localVariable;
        }
        var wrap2 = wrapValue2(2);
        var wrap3 = wrapValue2(3);
        console.log(wrap2);
        console.log(wrap3);
```
### 3.5 递归
```递归实例
    function power(base,exponent){
        if(exponent == 0){
            return 1;
        }else
        return base*power(base,exponent-1);
    }
    console.log(power(2,3));
```
注意：虽然递归函数看起来比较优雅，但是递归的执行效率比循环慢大约10倍，请根据实际情况使用。

### 3.6 纯函数
**纯函数**：一种只会产生值而不会影响它范围外任何事情的函数

## 第四章：数据结构：对象和数组
### 4.1 属性
    array.length == array["length"]
### 4.2 方法
```数组方法实例
     var arr = [];
       //push()：将元素插入到数组中
       arr.push("Mack");
       arr.push("the","Knife");
       console.log(arr);
       //join()：将字符数组拼接成单个字符串，中间用空格连接
       console.log(arr.join(" "));
       //pop()：取出最后一个元素并返回给调用者
       console.log(arr.pop());
       console.log(arr);
```
### 4.3 对象及delete & in
```
     var obj = {left:1,right:2};
      console.log(obj.left);
      //删除left属性
      delete obj.left;
      console.log(obj.left);//返回undefined
      //判断left是否还在obj中
      console.log("left" in obj);//返回false
```
### 4.4 对象的可变性
**引用两个相同对象和两个不同对象包含相同属性是有区别的**
```
    var obj1 = { value: 10 };
    var obj2 = { value: 10 };
    var obj3 = obj1;
    console.log(obj1 == obj2);//false
    console.log(obj1 == obj3);//true
    obj1.value = 20;
    console.log(obj1.value);//20
    console.log(obj2.value);//10
    console.log(obj3.value);//20
```









BOM:浏览器对象模型

url：统一资源定位符，相当于地址


# window对象

window对象为全局对象:相当于浏览器打开的窗口

window下的函数都可以省略window,直接调用

系统对话框
- alert():确定
- confirm():确定,取消
- prompt():输入框,确定,取消

window.open()
- open(url):打开新窗口,加载url
- open(url,name):打开新窗口,名字为name,加载url,如果再次加载,会在此窗口加载,不会重新再打开新的窗口
- open(url,name,set):第三个参数设置打开的页面

opener:表示当前窗口的父窗口的window对象,IE不支持

# location对象

提供和当前窗口加载的文档有关信息,还提供一些导航功能(相当于窗口的地址输入框)

location是window的属性,也是document的有关属性,因此都可以用.

## location的一些属性
- loaction.hash():设置锚点,url的#部分,实现页内跳转
- location.host:主机名:端口号,浏览器默认端口号为 8080
	- 端口号:当前电脑软件的唯一标识
- location.hostname:主机名 域名/IP
- location.href:整个url
- location.pathname:文件路径
- location.href:整个url
- location.port:端口号
- location.protocol:协议
	- 协议:http-网络协议 file-本地协议 
- location.search:url?后面的部分,表示检索数据 

## location的一些方法
- assign():跳转到指定url
- reload():重新加载当前的url,如果传参为true时,会强制加载
	- 强制加载:从服务器源头开始加载,不使用浏览器缓存
- replace():用新的url替换当前url
	- 不同于assign,可以避免产生跳转前的历史记录


# URL统一资源定位符

protocol(协议):host(主机名):port(端口号)/pathname(路径)?search(查询字符串)#hash(锚点)

例子: http://www.baidu.com:8080/code/XXX.html?username=xxx&age=18#p1

# history
history：window的属性，用于保存用户的上网记录

## 属性
history.length	history对象的记录数(当前窗口浏览过的跳转记录)

## 方法
- .back():返回上一条历史纪录
- .forward():前进下一条记录
- .go():
	- 参数: 0 重载页面;正数 前进对应的记录;负数 后退对应的记录



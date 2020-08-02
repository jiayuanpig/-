Cookie

HTTP协议：超文本传输协议，用于从web服务器传输超文本到本地浏览器的传输协议，它是无状态协议

cookie：缓存在本地客户端的数据

# cookie的基本操作

增 删 查 改

- 查看cookie
	- document.cookie
- 设置cookie
	- 设置内容:document.cookie = "username=Tony";
	- 设置有效期
		- var oDate = new Date();oDate.setDate(oDate.getDate()+3);
		- document.cookie = "username=Tony;expires=" + oDate;
- 修改cookie:直接赋值即可修改
- 删除cookie
	- 将有效期设置为过去的时间,就可以将cookie删除

cookie操作封装
```js
	//设置cookie
	function setCookie(name,value,day){
		var oDate = new Date();
		oDate.setDate(oDate.getDate() + day);
		document.cookie = name + "=" + value + ";expires=" + oDate;
	}
	//根据属性名来获取cookie值
	function getCookie(name){
		var str = document.cookie;
		var arr = str.split("; ");
		for (var i = 0; i < arr.length; i++) {
			var arr1 = arr[i].split("=");
			if(arr1[0] == name){
				return arr1[1];
			}
		}
	}
	//删除cookie
	function removeCookie(name){
		setCookie(name,1,-1);
	}
```

# cookie实例:七天免登陆

```html
	<html>
	    <head>
	        <title>七天免登陆</title>
			<script>
				//设置cookie
				function setCookie(name,value,day){
					var oDate = new Date();
					oDate.setDate(oDate.getDate() + day);
					document.cookie = name + "=" + value + ";expires=" + oDate;
				}
				//根据属性名来获取cookie值
				function getCookie(name){
					var str = document.cookie;
					var arr = str.split("; ");
					for (var i = 0; i < arr.length; i++) {
						var arr1 = arr[i].split("=");
						if(arr1[0] == name){
							return arr1[1];
						}
					}
				}
				//删除cookie
				function removeCookie(name){
					setCookie(name,1,-1);
				}
			</script>
	    </head>
	    <body>
	        用户名:<input type="text" />
			密码:<input type="password" />
			<label>
				<input type="checkbox" />七天免登录
			</label>
			<input type="button" value="登陆" />
			
			<script>
				var aInput = document.getElementsByTagName("input");
				//判断cookie是否存在
				if(getCookie("username")){
					aInput[0].value = getCookie("username");
					aInput[1].value = getCookie("password");
				}
				// 设置登录事件
				aInput[3].onclick = function(){
					//获取用户名,密码
					var username = aInput[0].value;
					var password = aInput[1].value;
					//判断是否点击了七天免登陆
					if(aInput[2].checked){
						//设置cookie
						setCookie("username",username,7);
						setCookie("password",password,7);
					}else{
						//删除cookie
						setCookie("username",username,-1);
						setCookie("password",password,-1);
					}
					console.log(document.cookie);
				}
			</script>
	    </body>
	</html>

```




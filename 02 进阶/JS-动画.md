JS动画

- JS动画原理(不断改变html的样式,使其达到动态的效果)
	- 匀速
	- 碰撞
		- 与边界碰撞
		- 与其他元素碰撞(当两个元素的中心同时满足小于宽的和的一半以及高的和的一半,就发生了碰撞)
- 动画函数封装
	- getStyle
	- 减速
	- 透明度
	- 多属性
- 轮播
	- 透明度
	- 水平


# JS 封装函数

```js
	function getStyle(el,property){
		return getComputedStyle(el)[property];
	}
	//对单个属性进行处理
	function animate(el,property,target){//动画先快后慢
		clearInterval(el.timerId);
		el.timerId = setInterval(function(){
			var current;
			if(property == "opacity"){
				current = Math.round(parseFloat(getStyle(el,property))*100);
			}else{
				current = parseInt(getStyle(el,property));
			}
			
			var speed = (target - current)/30;
			speed = speed > 0?Math.ceil(speed):Math.floor(speed);
			
			if(property == "opacity"){
				el.style["opacity"] = (current + speed)/100;
			}else{
				el.style[property] = current + speed + "px";
			}
			
		},20);
	}
	
	//对多个属性进行处理
	function animate(el,properties){//动画先快后慢
		clearInterval(el.timerId);
		el.timerId = setInterval(function(){
			
			for(var property in properties){
				var current;
				var target = properties[property];
				if(property == "opacity"){
					current = Math.round(parseFloat(getStyle(el,property))*100);
				}else{
					current = parseInt(getStyle(el,property));
				}
				var speed = (target - current)/30;
				speed = speed > 0?Math.ceil(speed):Math.floor(speed);
				
				if(property == "opacity"){
					el.style["opacity"] = (current + speed)/100;
				}else{
					el.style[property] = current + speed + "px";
				}
			}
		},20);
	}
	
	
```



















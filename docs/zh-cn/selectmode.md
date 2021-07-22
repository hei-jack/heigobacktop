# 选择模式

HeiGoBackTop内置了`0跳转顶部、1跳转底部、2慢滑到顶部、3慢滑到底部`的四种模式，方便用户结合网站需求自行选择。

## 跳转顶部

默认模式就是跳转到顶部，用户点击按钮直接返回到顶部。

```javascript
let example = new HeiGoBackTop(0);

//或者

example.onBeforeCreate(function(){
    this.mode = 0;
});
```

## 跳转底部

用户点击按钮之后直接跳转到页面底部。

只需要将上面方式中的`0`改为`1`即可。

## 慢滑到顶部

用户点击之后，将会根据设置的速度和滑动距离慢慢滑动到顶部。

```javascript
let example = new HeiGoBackTop(2); //默认的滑动速度是每500毫秒滑动100px的距离

example.onBeforeCreate(function(){
    this.speed = 1000; //更改滑动速度为1秒
    this.distance = 300px; //更改每次滑动距离为300px
});
```

## 慢滑到底部

用户点击之后，将会根据设置的速度和滑动距离慢慢滑动到页面底部。

只需将慢滑到顶部的示例`2`改为`3`即可。

## 顶部和底部模式切换

HeiGoBackTop发布以后，有人建议，如果能自动识别是跳转页面顶部还是底部就更好了。

比较懒，暂时不想动了，现在先提供一个简陋的实现方案，等真正有这个需求的人多起来之后会考虑在以后的版本更迭中实现。

方案如下:

```javascript
var hello = new HeiGoBackTop();
//在创建之前执行
hello.onBeforeCreate(function() {
	//劫持原来的binOn方法 方便将按钮的点击事件注册为一次性临时事件
	this.bindOn = function(el, event, func) {
		if (func === undefined) return false;
		this.register(el, event, func); //bind方法改变this指向 否则绑定全局事件时会指向window全局对象
	};

	//新增register绑定方法 如果绑定的是按钮 就注册为一次性临时事件
	this.register = function(el, event, func) {
		if (el === this.btn) {
			//如果是按钮注册事件
			var that = this; //改变this指向
			el.addEventListener(event,function handler() {
				func.apply(that, arguments);
				el.removeEventListener(event, handler, false);
			},false);
			return true;
		}
		this.addEventListener(el, event, func.bind(this));
	};
    
    this.show_height = 0;
});

//在滑动到页面底部或者顶部时执行
hello.onScrollOver(function() {
    //判断是页面顶部还是底部
	var flag = this.getScrollTop() === 0;
	var text = flag ? '返回底部': '返回顶部';
    //注册一次性事件
	flag ? this.register(this.btn, "click", this.goDown) : this.register(this.btn, "click", this.goBackTop);     //更改对应文本
	this.btn.getElementsByTagName('button')[0].textContent = text;
});
```


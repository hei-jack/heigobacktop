# Select Mode

HeiGoBackTop has built-in four modes: `0 jump to the top, 1 jump to the bottom, 2 slow to the top, and 3 slow to the bottom`, which is convenient for users to choose according to the needs of the website.

## Jump to the top

The default mode is to jump to the top, and the user clicks the button to return directly to the top.

```javascript
let example = new HeiGoBackTop(0);

//or

example.onBeforeCreate(function(){
    this.mode = 0;
});
```

## jump to the bottom

After the user clicks the button, it jumps directly to the bottom of the page.

Just change `0` in the above method to `1`.

## Slow to the top

After the user clicks, it will slowly slide to the top according to the set speed and sliding distance.

```javascript
let example = new HeiGoBackTop(2); //The default sliding speed is 100px distance every 500 milliseconds

example.onBeforeCreate(function(){
    this.speed = 1000; //Change the sliding speed to 1 second
    this.distance = 300px; //Change the distance of each sliding to 300px
});
```

## Slowly to the bottom

After the user clicks, it will slowly slide to the bottom of the page according to the set speed and sliding distance.

Just change the example of slow sliding to the top `2` to `3`.

## Top and bottom mode switching

After the release of HeiGoBackTop, someone suggested that it would be better if it can automatically identify whether it is to jump to the top or bottom of the page.

I'm lazy, I don't want to move for the time being. Now I will provide a simple implementation plan. When more people really have this need, I will consider implementing it in future version changes.

The plan is as follows:

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
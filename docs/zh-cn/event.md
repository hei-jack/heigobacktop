# 内置事件

HeiGoBackTop设计之初就为开发者考虑了一些使用场景，借助内置事件，开发者能够更快满足自己的项目需求。

HeiGoBackTop的内置事件主要分为两种，一种是[一次性临时事件](#一次性临时事件)，另外一种是[持续事件](#持续事件)。

## 一次性临时事件

[onBeforeCreate](/zh-cn/configuration#内置事件)和[onAfterCreate](/zh-cn/configuration#内置事件)事件就是典型的一次性临时事件，如果你绑定了对应事件，将在HeiGoBackTop初始化之前或初始化结束自动触发，触发之后自动销毁。

```javascript
let example = new HeiGoBackTop();

example.onBeforeCreate(function(){
	console.log('我要创建了');
});

example.onAfterCreate(function(){
	console.log('我要创建完了');
});
```

## 持续事件

[onShow](/zh-cn/configuration#内置事件)和[onHide](/zh-cn/configuration#内置事件)就是典型的持续事件，如果你绑定了对应事件，在每次按钮显示或隐藏时触发。

```javascript
example.onShow(function(){
	console.log('按钮显示了，你想做点什么呢？');
});

example.onHide(function(){
	console.log('按钮隐藏了，你想做点什么呢？');
});
```

更多事件请查看[配置项](/zh-cn/configuration#内置事件)
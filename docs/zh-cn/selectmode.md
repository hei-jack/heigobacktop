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
# 定制样式

HeiGoBackTop提供很多快捷定制按钮样式和主题的方式，非凡体验，一秒到手。

简单到哭的使用方式，例如最简单的切换主题方式，只需要在[快速开始](/zh-cn/quickstart)的基础上多加一句代码。

## 切换主题

```javascript
//初始化 如果没有传入或更改参数 一般都是默认的主题和尺寸大小等
let example = new HeiGoBackTop();  

//切换主题最简单的方式 默认主题是0 此时我们直接更改参数切换为2号主题
example.themes = 2;

//推荐使用下面这种方式切换主题和其他参数
example.onBeforeCreate(function(){
    this.themes = 2;
});

//如果你同时使用了上面两种方式 那么后面这种方式会覆盖第一种方式
```



## 按钮尺寸

很多时候，默认的尺寸也许无法满足你的胃口，当然，这也不会花费你几秒的时间。

你只需要像下面这样

```javascript
let example = new HeiGoBackTop(); 

example.onBeforeCreate(function(){
    this.width = '200px'; //修改按钮宽度为200px 默认宽度为150px
    
    //或者这样
    this.width = '200vw'; //修改按钮宽度为200vw
    
    this.height = '50px'; //修改按钮高度为50px 默认高度是40px
    
    //如果你修改了高度请记得务必一起修改圆角尺寸 否则可能...
    this.radius = '50px';
});
```

## 按钮文本

按钮显示的文字，你也可以自由发挥。

```javascript
let example = new HeiGoBackTop(); 

example.onBeforeCreate(function(){
    this.text = '你好';
    this.text_color = '#000';
});
```

## 按钮位置

决定按钮显示的位置。

```javascript
let example = new HeiGoBackTop(); 

example.onBeforeCreate(function(){
    this.top = '80%';
    this.right = '10%';
});
```

## 按钮颜色

自己选择喜欢的颜色。

```javascript
let example = new HeiGoBackTop(); 
example.onBeforeCreate(function(){
    this.color = '#000';
    this.shadow = '0 4px 15px 0 rgba(462, 358, 123,0.75)'; //阴影
});
```

## 自定义挂载元素

一般情况下，不建议小白自定义挂载元素。因为自定义挂载元素，就意味着无法使用HeiGoBackTop预定义的主题和所有与按钮样式相关的属性。

为了避免冲突，默认的挂载元素是id为`__go-back-top`的元素，会在HeiGoBackTop初始化时自动创建。

```html
//自定义挂载元素
<button id="hello" style="background:red;">去哪儿</button>

<script>
let example = new HeiGoBackTop(); 

example.onBeforeCreate(function(){
    this.el = '#hello'; //只支持传入元素id
});
    
//或者你也可以在初始化时去定义
let example = new HeiGoBackTop(0,'hello'); 
</script>
```

更多参数和用法请查看[配置项](/zh-cn/configuration)
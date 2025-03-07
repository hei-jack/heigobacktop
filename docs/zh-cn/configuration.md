# 配置项

HeiGoBackTop所有参数和事件都在这里，你可以尽情发挥了。

## 初始化参数

初始化参数可以在HeiGoBackTop实例化时选择传入。

`HeiGoBackTop(mode,el,speed,distance);`

### mode

参数类型`int`

默认值`0`

0-3对应分别对应四种模式。详见[选择模式](/zh-cn/selectmode);

### el

参数类型`string`

默认值`#__go-back-top`

HeiGoBackTop初始化时挂载元素。

如果你想要自定义挂载元素，请查看[自定义挂载元素](/zh-cn/customstyle#自定义挂载元素)

### speed

参数类型`int`

默认值`500`

滚动速度，间隔多少毫秒开始滚动。只有在`2慢滑到顶部 3慢滑到底部模式时生效`。

### distance

参数类型`int`

默认值`100`

滚动距离，每次滚动的距离。只有在`2慢滑到顶部 3慢滑到底部模式时生效`。

### smooth

参数类型 `bool`

默认值`true`

平滑的滚动到顶部或者底部，默认打开，`0 和 1 模式生效`.

## 属性

列出的所有属性，都建议在[onBeforeCreate](#onBeforeCreate(callBack))事件更改。

### show_height

参数类型`int`

默认值`400`

规定按钮在滚动高度达到什么位置时显示。

需要注意的是，如果该值为负值或0可能会对[onShow](#内置事件)和[onHide](#内置事件)事件造成影响。

### width

参数类型`string`

默认值`150px`

规定按钮的宽度。值可以参考`css width`属性值。

### height

参数类型`string`

默认值`40px`

规定按钮的宽度。值可以参考`css height`属性值。

### top

参数类型`string`

默认值`90%`

规定按钮的显示到浏览器顶部的距离。值可以参考`css top`属性值。

适用于V1.0.2及以下版本。

### bottom

参数类型`string`

默认值`5%`

规定按钮的显示到浏览器底部的距离。值可以参考`css bottom`属性值。

适用于V1.0.3及以上版本。

### right

参数类型`string`

默认值`5%`

规定按钮的显示到浏览器右侧的距离。值可以参考`css right`属性值。

### radius

参数类型`string`

默认值`40px`

规定按钮的圆角大小。值可以参考`css3 border-radius`属性值。

### text

参数类型`string`

默认值`返回顶部`

规定按钮的显示的文字。

### text_color

参数类型`string`

默认值`#fff`

规定按钮文字显示的颜色。

### themes

参数类型`int`

默认值`0`

规定按钮显示的主题和鼠标移入的动画。值范围`0-11`。

### color

参数类型`string`

默认值`linear-gradient(to right,#6966ff,#37e2d3,#63e8dd,#ccff66)`

规定按钮的背景颜色。

需要注意是，此属性只有在[themes](#themes)属性值为0，也就是默认主题时才有效。

### shadow

参数类型`string`

默认值`0 4px 15px 0 rgba(41, 163, 163,0.75)`

规定按钮边缘的阴影。

需要注意是，此属性只有在[themes](#themes)属性值为0，也就是默认主题时才有效。

### mode

参考初始化参数[mode](#初始化参数)

### el

参考初始化参数[el](#初始化参数)

### speed

参考初始化参数[speed](#初始化参数)

### distance

参考初始化参数[distance](#初始化参数)

## 内置事件

### onBeforeCreate(callBack)

一次性临时事件。

在HeiGoBackTop初始化之前自动触发。

### onAfterCreate(callBack)

一次性临时事件。

在HeiGoBackTop初始化完成之后自动触发。

### onShow(callBack)

持续事件。

当按钮显示时触发此事件。

需要注意的是如果[show_height](#show_height)参数如果设置为0或负数，可能[onShow](#onShow(callBack))事件和[onHide](#onHide(callBack))事件只会触发一次，或者不会触发。

### onHide(callBack)

持续事件。

当按钮隐藏时触发此事件。

### onScroll(callBack)

持续事件。

当页面发生滚动时，无论是用户主动滑动，还是慢滑模式的自动滑动，都会触发此事件。

此事件执行极为频繁，使用时请谨慎。

### onScrollOver(callBack)

持续事件。

当`用户点击按钮后`到达页面顶部或者底部时触发此事件。

四种模式都会触发，触发位置有所不同。

例如[跳转顶部](/zh-cn/selectmode#跳转顶部)模式的触发就是到达顶部时执行，而[慢滑到底部](/zh-cn/selectmode#慢滑到底部)模式就是到达页尾触发。
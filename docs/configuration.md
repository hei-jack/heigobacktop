# Configuration

All the parameters and events of HeiGoBackTop are here, so you can play to your heart's content.

## Initialization parameters

The initialization parameters can be replaced when HeiGoBackTop is instantiated.

`HeiGoBackTop(mode,el,speed,distance,smooth);`

### mode

type`int`

defaults`0`

0-3 corresponds to the four modes respectively.You can check [Select Mode](/selectmode).

### el

type`string`

defaults`#__go-back-top`

Mount elements when HeiGoBackTop is initialized.

If you want to customize the mount element，You can check [Custom mount elements](/customstyle).

### speed

type`int`

defaults`500`

Scrolling speed, the interval between milliseconds to start scrolling. It only takes effect when `2Slow slide to the top 3Slow to the bottom mode`.

### distance

type`int`

defaults`100`

The distance of each scroll. the interval between milliseconds to start scrolling. It only takes effect when `2Slow slide to the top 3Slow to the bottom mode`.

### smooth

type `bool`

defaults`true`

Smooth return to the top or bottom, which is on by default.`0 and 1` modes in effect.

## Attributes

All the properties listed are recommended to be changed in the [onBeforeCreate](#) event.

### show_height

type`int`

defaults`400`

Specifies where the button is displayed when the scroll height reaches.

It should be noted that if the value is negative or 0, it may affect the [onShow](#) and [onHide](#) events.

### width

type`string`

defaults`150px`

Specifies the width of the button. The value can refer to the `css width` property value.

### height

type`string`

defaults`40px`

Specifies the width of the button. The value can refer to the `css height` property value.

### top

type`string`

defaults`90%`

Specifies the distance from the display of the button to the top of the browser. The value can refer to the `css top` property value.

### right

type`string`

defaults`5%`

Specifies the distance from the display of the button to the right side of the browser. The value can refer to the `css right` property value.

### radius

type`string`

defaults`40px`

Specifies the rounded corner size of the button. The value can refer to the `css3 border-radius` property value.

### text

type`string`

defaults`返回顶部`

Specifies the text displayed on the button.

### text_color

type`string`

defaults`#fff`

Specifies the color of the button text display.

### themes

type`int`

defaults`0`

Specifies the theme of the button display and the animation of the mouse moving in. The value range is `0-11`.

### color

type`string`

defaults`linear-gradient(to right,#6966ff,#37e2d3,#63e8dd,#ccff66)`

Specifies the background color of the button.

It should be noted that this attribute is only valid when the [themes](#themes) attribute value is 0, which is the default theme.

### shadow

type`string`

defaults`0 4px 15px 0 rgba(41, 163, 163,0.75)`

Specifies the shadow on the edge of the button.

It should be noted that this attribute is only valid when the [themes](#themes) attribute value is 0, which is the default theme.

### mode

Refer to initialization parameters[mode](#)

### el

Refer to initialization parameters[el](#)

### speed

Refer to initialization parameters[speed](#)

### distance

Refer to initialization parameters[distance](#)

## Built-in event

### onBeforeCreate(callBack)

One-time temporary event.

Triggered automatically before HeiGoBackTop is initialized.

### onAfterCreate(callBack)

One-time temporary event.

It is triggered automatically after HeiGoBackTop initialization is completed.

### onShow(callBack)

Continuous events.

This event is triggered when the button is displayed.

It should be noted that if the [show_height](#show_height) parameter is set to 0 or a negative number, the [onShow](#) event and [onHide](#) event may only be triggered once, or Will not trigger.

### onHide(callBack)

Continuous events.

This event is triggered when the button is hidden.

### onScroll(callBack)

Continuous events.

When the page is scrolled, whether it is the user's active sliding or the automatic sliding of the slow sliding mode, this event will be triggered.

This event is executed very frequently, please be cautious when using it.

### onScrollOver(callBack)

Continuous events.

This event is triggered when `user clicks the button` to reach the top or bottom of the page.

All four modes will trigger, and the trigger position is different.

For example, the trigger of [jump to top](/selectmode) mode is executed when it reaches the top, and [slow to bottom](/selectmode) mode is to reach Footer trigger.
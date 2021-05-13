# Custom Style

HeiGoBackTop provides many quick ways to customize button styles and themes, an extraordinary experience, one second.

The simple way to use it, such as the simplest way to switch themes, just need to add one more code on the basis of [Quick Start](/quickstart).

## Switch theme

```javascript
//Initialization If no parameters are passed in or changed, it is generally the default theme and size, etc.
let example = new HeiGoBackTop();  

//The easiest way to switch themes. The default theme is 0. At this time, we directly change the parameters and switch to theme 2.
example.themes = 2;

//It is recommended to use the following method to switch themes and other parameters
example.onBeforeCreate(function(){
    this.themes = 2;
});

//If you use the above two methods at the same time, the latter method will override the first method
```



## Button size

In many cases, the default size may not satisfy your appetite, of course, it will not take you a few seconds.

You just need to be like below

```javascript
let example = new HeiGoBackTop(); 

example.onBeforeCreate(function(){
    this.width = '200px'; //Modify the button width to 200px,The default width is 150px
    
    //或者这样
    this.width = '200vw'; //Modify the button width to 200vw
    
    this.height = '50px'; //Modify the button height to 50px,The default width is 40px
    
    //If you modify the height, please remember to modify the fillet size together, otherwise it may...
    this.radius = '50px';
});
```

## Button text

You can also set the text displayed on the button freely.

```javascript
let example = new HeiGoBackTop(); 

example.onBeforeCreate(function(){
    this.text = 'hello';
    this.text_color = '#000';
});
```

## Button position

Decide where the button is displayed.

```javascript
let example = new HeiGoBackTop(); 

example.onBeforeCreate(function(){
    this.top = '80%';
    this.right = '10%';
});
```

## Button color

Choose the color you like.

```javascript
let example = new HeiGoBackTop(); 
example.onBeforeCreate(function(){
    this.color = '#000';
    this.shadow = '0 4px 15px 0 rgba(462, 358, 123,0.75)'; //shadow
});
```

## Custom mount elements

Under normal circumstances, it is not recommended that rookies customize mount elements. Because customizing the mount element means that HeiGoBackTop's predefined themes and all button style-related attributes cannot be used.

To avoid conflicts, the default mount element is the element with id `__go-back-top`, which will be automatically created when HeiGoBackTop is initialized.

```html
<!-- Custom mount elements -->
<button id="hello" style="background:red;">where to</button>

<script>
let example = new HeiGoBackTop(); 

example.onBeforeCreate(function(){
    this.el = '#hello'; //Only support the incoming element id
});
    
//Or you can define it during initialization
let example = new HeiGoBackTop(0,'hello'); 
</script>
```

For more parameters and usage, please check [Configuration](/configuration)
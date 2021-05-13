# More

Maybe you can explore more useful usages.

## Use in Tampermonkey

You can directly search in `greasy fork` assistant `返回顶部小助手` , or [click here](https://greasyfork.org/zh-CN/scripts/426408-返回顶部小助手) to install.

Or you can directly use `// @require https://greasyfork.org/scripts/426407-heigobacktop-js/code/HeiGoBackTopjs.js?version=930565` in your custom script.

## Use in Chrome Tools

- Create files and folders with the following structure

```
- HeiGoBackTop
  -- img
    --- icon16.png
    --- icon28.png
    --- icon128.png
  -- js
    --- heigobacktop.min.js
  -- manifest.json
  -- options.html
  -- popup.html
```

`img file path is used to store the expansion icon`

`manifest.json`

```javascript
{
	"manifest_version": 2,
	"name": "HeiGoBackTop",
	"version": "1.0.0",
	"description": "HeiGoBackTopV1.0.0",
	"icons":
	{
		"16": "img/icon16.png",
		"48": "img/icon48.png",
		"128": "img/icon128.png"
	},
	"browser_action": 
	{
		"default_icon": "img/icon16.png",
		"default_title": "HeiGoBackTop",
		"default_popup": "popup.html"
	},
	"permissions":
	[
		"contextMenus",
		"tabs", 
		"notifications", 
		"webRequest", 
		"webRequestBlocking",
		"storage", 
		"http://*/*", 
		"https://*/*" 
	],
	"homepage_url": "https://github.com/hei-jack/heigobacktop/",
	"options_page": "options.html",
	"options_ui":
	{
		"page": "options.html",
		"chrome_style": true
	},
	"content_scripts": [
    {
      "matches": ["http://*/*", "https://*/*"],
      "js": ["./js/heigobacktop.min.js"]
    }
  ]
}
```

`options.html`

```html
<!DOCTYPE html>
<html>
<head>
	<meta charset = "utf-8"/>
	<title>快捷菜单</title>
	<style>
		*{padding:0;margin:0;}
		p{width:100px;padding:5px 0 10px;}
	</style>
</head>
<body>
<p>Edible method: please check for details https://hei-jack.github.io/heigobacktop/</p>
</body>
</html>
```

`popup.html`

```html
<!DOCTYPE html>
<html>
<head>
	<meta charset = "utf-8"/>
	<title>返回顶部助手-拓展选项页</title>
	<style>
     *{padding: 0;margin: 0;}
	 .main{width:80%;margin:5px 10% 0 10%;}
	 .title{width:100%;font-family: "Microsoft YaHei";height:100px;text-align:center;line-height:100px;}
	 a{color:red;font-size:14px;}
	</style>
</head>
<body>
	<div class="main">
		<div class="title">
            <a href="https://hei-jack.github.io/heigobacktop/">please check docs</a>
		</div>
	</div>
</body>
</html>
```



`heigobacktop.min.js`

```javascript
//将heigobacktop.min.js代码复制到这
var hello = new HeiGoBackTop(); //然后实例化并进行其他操作
```

`Open Google Chrome ==> More tools ==> Extension program ==> Open developer mode ==> Load the decompressed program (path selection HeiGoBackTop) ==> Open the webpage and go down to experience heigobacktop`
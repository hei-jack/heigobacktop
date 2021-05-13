# 更多用法

也许你还能探索出更多有用的用法。

## 在油猴插件中使用

你可以直接在`greasy fork`搜索返回顶部小助手，或者[点击这里](https://greasyfork.org/zh-CN/scripts/426408-返回顶部小助手)前往安装。

或者你也可以直接在你自定义的脚本中使用`// @require https://greasyfork.org/scripts/426407-heigobacktop-js/code/HeiGoBackTopjs.js?version=930565`。

## 在谷歌浏览器插件中使用

- 创建如下结构的文件和文件夹

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

`img文件下用于存放拓展图标`

`manifest.json`

```javascript
{
	"manifest_version": 2,
	"name": "返回顶部助手",
	"version": "1.0.0",
	"description": "返回顶部助手V1.0.0",
	"icons":
	{
		"16": "img/icon16.png",
		"48": "img/icon48.png",
		"128": "img/icon128.png"
	},
	"browser_action": 
	{
		"default_icon": "img/icon16.png",
		"default_title": "返回顶部助手",
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
<p>食用方法：详情请查看https://hei-jack.github.io/heigobacktop/</p>
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
            <a href="https://hei-jack.github.io/heigobacktop/">返回顶部助手文档</a>
		</div>
	</div>
</body>
</html>
```



`heigobacktop.min.js`

```javascript
//Copy the heigobacktop.min.js code here
var hello = new HeiGoBackTop(); //Then instantiate and perform other operations
```

`打开谷歌浏览器 ==> 更多工具 ==> 拓展程序 ==> 打开开发者模式 ==> 加载已经解压的程序(路径选择HeiGoBackTop) ==> 打开网页下滑体验heigobacktop`


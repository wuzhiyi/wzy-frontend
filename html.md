##HTML 学习笔记

[HTML 学习进度](http://www.w3school.com.cn/html/html_responsive.asp)<br>
[HTML5 学习进度](http://www.w3school.com.cn/html5/index.asp)<br>

###2017-1-2

HTML 中新的结构/语义标签，[3wshool传送门](http://www.w3school.com.cn/html/html5_new_elements.asp)：

- header
- main
- footer
- figure, figcaption
- aside

###2016-12-23

在 HTML5 中显示视频：

	<video src="movie.ogg" controls="controls">
	</video>

controls 属性供添加播放、暂停和音量控件。

canvas 元素本身是没有绘图能力的，所有的绘制工作必须在 JavaScript 内部完成。

`getContext("2d")` 对象是内建的 HTML5 对象，拥有多种绘制路径、矩形、圆形、字符以及添加图像的方法。

Canvas 与 SVG 的比较：

Canvas：

- 依赖分辨率
- 不支持事件处理器
- 弱的文本渲染能力
- 能够以 .png 或 .jpg 格式保存结果图像
- 最适合图像密集型的游戏，其中的许多对象会被频繁重绘

SVG：

- 不依赖分辨率
- 支持事件处理器
- 最适合带有大型渲染区域的应用程序（比如谷歌地图）
- 复杂度会减慢渲染速度（任何过度使用 DOM 的应用都不快）
- 不适合游戏应用

HTML5 使用 getCurrentPosition() 方法来获得用户的位置

HTML5 提供了两种在客户端存储数据的新方法：

- localStorage - 没有时间限制的数据存储
- sesionStorage - 针对一个 session 的数据存储

存储数据实例：

	//localStorage
	<script type="text/javascript">
		localStorage.lastname="Smith";
		document.write(localStorage.lastname);
	</script>
	//sessionStorage
	<script type="text/javascript">
		sessionStorage.lastname="Smith";
		document.write(sessionStorage.lastname);
	</script>

如需启用应用程序缓存，请在存档的 <html> 标签中包含 `manifest` 属性，如下：

	<!DOCTYPE HTML>
	<html manifest="demo.appcache">
	...
	</html>

manifest 文件的建议的文件扩展名是：`.appcache`

manifest 文件可分为三个部分：

1. CACHE MANIFEST：在此标题下列出的文件将在首次下载后进行缓存
2. NETWORK：在此标题下列出的文件需要与服务器的连接，且不会被缓存
3. FALLBACK：在此标题下列出的文件规定当页面无法访问时的回退页面（比如 404 页面）

实例，完整的 manifest 文件

	CACHE MANIFEST
	# 2012-02-21 v1.0.0
	/theme.css
	/logo.gif
	/main.js

	NETWORK:
	login.asp

	FALLBACK:
	/html5/ /404.html

适用于大多数 HTML 元素的属性：

- `class`：规定元素的类名(classname)
- `id`：规定元素的唯一 id
- `style`：规定元素的行内样式(inline style)
- `title`：规定元素的额外信息（可在工具提示中显示）

`<hr />` 标签在 HTML 页面中创建水平线。hr 元素可用于分割内容。

HTML 注释语法：`<!-- This is a comment -->`

HTML 的引用(quotation)

- `<q>`：定义短的引用
- `<blockquote>`：定义被引用的节
- `<abbr>`：定义缩写或首字母缩略语
- `<dfn>`：定义项目或缩写的定义
- `<address>`：定义文档或文章的联系信息（作者/拥有者）
- `<cite>`：定义著作的标题
- `<bdo>`：定义文本方向/双流向覆盖(bi-directional override)

HTML 计算机代码元素：

- `<code>`：定义计算机代码文本
- `<kbd>`：定义键盘文本
- `<samp>`：定义计算机代码示例
- `<var>`：定义变量
- `<pre>`：定义预格式化文本

外部样式表：

	<head>
		<link rel="stylesheet" type="text/css" href="style.css">
	</head>

用图片作为链接：

	<a href="index.html" target="_blank">
		<img border="0" src="images/pic.png" />
	</a>

HTML 链接 - name 属性

- name 属性规定锚(anchor) 的名称
- 可以使用 name 属性创建 HTML 页面中的书签
- 当使用命名锚(named anchors) 时，可以创建直接跳至该命名锚（比如页面中某个小节）的链接，这样使用者就无需不停地滚动页面来寻找他们需要的信息了。

命名锚的语法：`<a name="label">锚（显示在页面上的文本）</a>`

可以使用 id 属性来替代 name 属性，命名锚同样有效	

指向锚的链接：`<a href="#tips">有用的提示</a>`<br />
在其他页面中创建指向该锚的链接：`<a href="https://www.abc.com/html/html_links.asp#tips">有用的提示</a>`

`<span>` 元素是内联元素，可用作文本的容器。

HTML5 语义元素

- `header`：定义文档或节的页眉
- `nav`：定义导航链接的容器
- `section`：定义文档中的节
- `article`：定义独立的自包含文章
- `aside`：定义内容之外的内容（比如侧栏）
- `footer`：定义文档或节的页脚
- `details`：定义额外的细节
- `summary`：定义 details 元素的标题

引用 bootstrap 框架

	<head>
	<link rel="stylesheet" href="http://maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css">
	</head>
	<body>
	<div class="container">
	...
	</div>
	</body>

框架结构标签(<frameset>)

- 框架结构标签 (<frameset>) 定义如何将窗口分割为框架
- 每个 frameset 定义了一系列行或列
- rows/columns 的值规定了每行或每列占据屏幕的面积

iframe 标签定义内联的子窗口（框架）

<title> 标签定义文档的标题，title 元素在所有 HTML/XHTML 文档中都是必需的。title 元素能够：

- 定义浏览器工具栏中的标题
- 提供页面被添加到收藏夹时显示的标题
- 显示在搜索引擎结果中的页面标题



































#慕课网 JavaScript入门篇 学习笔记

###第2章 标签

-  `&nbsp;`: 在 HTML 中输入空格
- `<table summary="表格简介文本"`
- `<caption>标题文本</caption>`
- `<a href="目标网址" title="鼠标滑过显示的文本" target="_blank">链接显示的文本</a>`
- `<a href="mailto: url ? cc=url & bcc=url & subject=主题 & body=邮件内容">发送</a>`
- `<img src="图片地址" alt="下载失败时的替换文本" title="提示文本">`
- `<form method="传送方式" action="服务器文件">`
    - `type="text"`: 文本输入框
    - `type="password"`: 密码输入框
    - `name`: 为文本框命名，以备后台程序 ASP、PHP 使用
    - `value`: 为文本输入框设置默认值（一般起到提示作用）
    - `<textarea rows="行数" cols="列数">文本</textarea>`
- `type="radio"`: 控件为单选框，同一组的单选按钮，name 取值一定要一致，这样同一组的单选按钮才可以起到单选的作用
- `type="checkbox"`: 控件为复选框
- `type="reset"`: 按钮有重置作用
- `<label for="控件id名称">`: for 属性中的值应当与相关控件的 id 属性值一定要相同

###CSS

- `.first>span{border:1px solid red;}`: 子选择器
- `.first span{color:red}`: 包含选择器

注意区别：`>` 作用于元素的第一代后代，空格作用于元素的所有后代
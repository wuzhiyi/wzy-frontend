##JavaScript 学习笔记

[w3school 学习进度](http://www.w3school.com.cn/js/js_htmldom.asp)

###2016-12-21

相对引用地址格式

	<img src="images/XXX.png" />
	<img src="./images/XXX.png" />

浏览器默认边缘留白，要消除可以在 css 中加入

	Body {
		Margin: 0;
		Padding: 0;
	}

定义 class 内 a 格式：

	.class_name>a:link {}
	.class_name>a:visited {}
	.class_name>a:hover {}

Css 字体

1. `text-decoration` 下划线
2. `font-weight` 字体加粗
3. `font-size` 字体大小

###2016-12-22

从 JavaScript 访问某个 HTML 元素，可以使用 document.getElementById(id) 方法。使用 `id` 属性来表示 HTML 元素。

请使用 document.write() 仅仅向文档输出写内容。如果在文档已完成加载后执行 document.write，整个 HTML 页面将被覆盖。

JavaScript 可以对代码进行拆行：可以在文本字符串中使用反斜杠 `\` 对代码进行换行。例如

	document.write("Hello \
	World!");

JavaScript 单行注释以 `//` 开头，多行注释以 `/*` 开始，`/*` 结尾。

JavaScript 创建数组

	1)
	var cars=new Array();
	cars[0]="Audi";
	cars[1]="BMW";
	cars[2]="Volvo";
	2) condensed array
	var cars=new Array("Audi", "BMW", "Volvo");
	3) literal array
	var cars=["Audi", "BMW", "Volvo"];

JavaScript 对象：对象由花括号分割。在括号内部，对象的属性以名称和值对的形式 `(name:value)` 来定义。属性由逗号分隔：

	var person={firstname:"Bill", lastname:"Gates", id:5566};
	上例中的对象（person）有三个属性：firstname, lastname 和 id

对象属性有两种寻址方式：

	name=person.lastname;
	name=person["lastname"];

###2016-12-23

JavaScript 中所有事物都是对象：字符串、数字、数组、日期，等。在 JavaScript 中，对象是拥有属性和方法的数据。

访问对象属性的语法是：

	objectName.propertyName

调用对象的方法：

	objectName.methodName()

button 使用方法：

	<button onclick="myFunction()">text-content</button>

JavaScript 变量的生存期：

1. JavaScript 变量的生命期从它们被声明的时间开始
2. 局部变量会在函数运行后被删除
3. 全局变量会在页面关闭后被删除

如果把值赋给尚未声明的变量，该变量将被自动作为全局变量声明。例如 `carname="Volvo";` 将声明一个全局变量 carname，即使它在函数内执行。

如果把数字与字符串相加，结果将成为字符串

比较运算符

1. `==`：等于
2. `===`：全等（值和类型）
3. `!=`：不等于

逻辑运算符

1. `&&`：and
2. `||`：or
3. `!`：not

条件运算符：基于某些条件对变量进行赋值的条件运算符：

	variableName=(condition)?value1:value2;

获取时间：`Date().getHours();`

Switch 语句可以用来选择多个代码块中的一个执行：

	switch(n) {
		case 1:
			statement 1;
			break;
		case 2:
			statement 2;
			break;
		default:
			n 与 case 1 和 case 2 不同时执行的代码
	}

JavaScript 支持不同类型的循环：

1. `for`: 循环代码块一定的次数
2. `for/in`: 循环遍历对象的属性
3. `while`: 当指定的条件为 true 时循环指定的代码块
4. `do/while`: 同样当指定的条件为 true 时循环指定的代码块

JavaScript 错误：

1. `try`：语句测试代码块的错误
2. `catch`：语句处理错误
3. `throw`：语句创建自定义错误

`try` 语句允许我们定义在执行时进行错误测试的代码块；<br>
`catch` 语句允许我们定义当 `try` 代码块发生错误时，所执行的代码块。<br>
JavaScript 语句 `try` 和 `catch` 是成对出现的：

	try {
		//在这里运行代码
	}
	catch(err) {
		//在这里处理错误
	}

`throw` 语句允许我们创建自定义错误。正确的技术术语是：创建或抛出异常(exception)。如果把 `throw` 与 `try` 和 `catch` 一起使用能够控制程序流，并生成自定义的错误消息。

语法：`throw exception`

JavaScript 可用来在数据被送往服务器前对 HTML 表单中的这些输入数据进行验证。

必填（或必选）项目：下面的函数用来检查用户是否已填写表单中的必填（或必选）项目。假如必填或必选项为空，那么警告框会弹出，并且函数的返回值为 false，否则函数的返回值则为 true（意味着数据没有问题）：

	function validate_required(field,alerttxt) {
		with (field) {
			if (value==null||value=="") {
	  			alert(alerttxt);return false}
			else {return true}
		}
	}

E-mail 验证：下面的函数检查输入的数据是否符合电子邮件地址的基本语法。
意思就是说，输入的数据必须包含 @ 符号和点号(.)。同时，@ 不可以是邮件地址的首字符，并且 @ 之后需有至少一个点号：

	function validate_email(field,alerttxt) {
		with (field) {
			apos=value.indexOf("@")
			dotpos=value.lastIndexOf(".")
			if (apos<1||dotpos-apos<2) {
	  			alert(alerttxt);return false}
			else {return true}
		}
	}
























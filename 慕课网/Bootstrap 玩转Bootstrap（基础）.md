# Bootstrap 玩转Bootstrap（基础）
22+12+30+12=76
#### 最基本的HTML模板

bootstrap模板为使IE6、7、8版本（IE9以下版本）浏览器兼容html5新增的标签，引入下面代码文件即可。

    <script src="https://oss.maxcdn.com/libs/html5shiv/3.7.0/html5shiv.js"></script>

同理为使IE6、7、8版本浏览器兼容css3样式，引入下面代码：

    <script src="https://oss.maxcdn.com/libs/respond.js/1.4.2/respond.min.js"></script>

#### 排版

- `<small>`: 副标题
- `.lead`: 添加 "class=lead“” 突出显示，其作用是增大文本字号，加粗文本，而且对行高和 margin 也做相应的处理
- `<b><strong>`: 让文本直接加粗
- `<em><i>`：斜体
- `<strong><em>`：强调类名
    - `.text-muted`：提示，使用浅灰色（#999）
    - `.text-primary`：主要，使用蓝色（#428bca）
    - `.text-success`：成功，使用浅绿色(#3c763d)
    - `.text-info`：通知信息，使用浅蓝色（#31708f）
    - `.text-warning`：警告，使用黄色（#8a6d3b）
    - `.text-danger`：危险，使用褐色（#a94442）
- 对齐，四种类名：
    - `.text-left`：左对齐
    - `.text-center`：居中对齐
    - `.text-right`：右对齐
    - `.text-justify`：两端对齐
- `.list-unstyled`：去点列表
- `.list-inline`：内联列表
- `<dl>`：定义列表
- `.dl-horizontal`：水平定义列表（只有屏幕大于 768px 的时候，添加类名 ".dl-horizontal" 才具有水平定义列表效果

#### 代码

- `<code>`：来显示单行内联代码，一般针对于单个单词或单个句子的代码
- `<pre>`：来显示多行块代码，一般是针对于多行代码（成块代码）
- `<kbd>`：来显示用户输入代码，一般是表示用户要通过键盘输入的内容
- 不管使用哪种代码风格，在代码中碰到小于号（<）要使用硬编码 `&lt;` 来替代，大于号(>)使用 `&gt;` 来替代
- `.pre-scrollable`：控制代码块区域最大高度为340px，一旦超出这个高度，就会在Y轴出现滚动条

#### 表格

千万注意，你的`<table>`元素中一定不能缺少类名“table”<br/>
表格的类名添加，语法：`class="className0 className1 className2"`

- `.active`：表示当前活动的信息
- `.success`：表示成功或者正确的行为
- `.info`：表示中立的信息或行为
- `.warning`：表示警告，需要特别注意
- `.danger`：表示危险或者可能是错误的行为
- `.table-hover`：悬浮状态
- `.table`：基础表格
- `.table-striped`：斑马线表格
- `.table-bordered`：带边框表格
- `.table-condensed`：紧凑型表格
- `.table-responsive`：响应式表格

#### 表单

常见表单元素：

- 文本输入框
- 下拉选择框
- 单选按钮
- 复选按钮
- 文本域
- 按钮

- `.form-control`：定制效果
    - 宽度变成了100%
    - 设置了一个浅灰色（#ccc）的边框
    - 具有4px的圆角
    - 设置阴影效果，并且元素得到焦点之时，阴影和边框效果会有所变化
    - 设置了placeholder的颜色为#999
- `.form-horizontal`：水平表单
- `.form-inline`：内联表单

如果你要在input前面添加一个label标签时，会导致input换行显示。如果你必须添加这样的一个label标签，并且不想让input换行，你需要将label标签也放在容器“form-group”中，如：

    <div class="form-group">
        <label class="sr-only" for="exampleInputEmail2">Email address</label>
    </div>
    <div class="form-group">
        <inputtype="email" class="form-control" id="exampleInputEmail2" placeholder="Enter email">
    </div>

label标签运用了一个类名“sr-only”，标签没显示就是这个样式将标签隐藏了

为了让控件在各种表单风格中样式不出错，需要添加类名“form-control”

复选框 checkbox 和单选择按钮 radio，示例：

    <form role="form">
      <h3>案例1</h3>
      <div class="checkbox">
        <label>
          <input type="checkbox" value="">
          记住密码
        </label>
      </div>
      <div class="radio">
        <label>
          <input type="radio" name="optionsRadios" id="optionsRadios1" value="love" checked>
          喜欢
        </label>
      </div>
        <div class="radio">
        <label>
          <input type="radio" name="optionsRadios" id="optionsRadios2" value="hate">
          不喜欢
        </label>
      </div>

从上面的示例，我们可以得知：

- 不管是checkbox还是radio都使用label包起来了
- checkbox连同label标签放置在一个名为“.checkbox”的容器内
- radio连同label标签放置在一个名为“.radio”的容器内
- 如果checkbox需要水平排列，只需要在label标签上添加类名“checkbox-inline”
- 如果radio需要水平排列，只需要在label标签上添加类名“radio-inline”
- `input[type=“submit”]`
- `input[type=“button”]`
- `input[type=“reset”]`
- `<button>`
- `input-sm`:让控件比正常大小更小
- `input-lg`:让控件比正常大小更大

焦点状态是通过伪类“:focus”来实现

表单控件的禁用状态和普通的表单禁用状态实现方法是一样的，在相应的表单控件上添加属性“disabled”。<br/>
使用方法为：只需要在需要禁用的表单控件上加上“disabled”即可：

    <input class="form-control" type="text" placeholder="表单已禁用，不能输入" disabled>

如果legend中有输入框的话，这个输入框是无法被禁用的。

表单验证状态样式：

- `.has-warning`:警告状态（黄色）
- `.has-error`：错误状态（红色）
- `.has-success`：成功状态（绿色）
- 使用的时候只需要在form-group容器上对应添加状态类名

如果你想让表单在对应的状态下显示 icon 出来，只需要在对应的状态下添加类名“has-feedback”。请注意，此类名要与“has-error”、“has-warning”和“has-success”在一起：

    <form role="form">
    <div class="form-group has-success has-feedback">
      <label class="control-label" for="inputSuccess1">成功状态</label>
      <input type="text" class="form-control" id="inputSuccess1" placeholder="成功状态" >
      <span class="glyphiconglyphicon-ok form-control-feedback"></span>
    </div>
    <div class="form-group has-warning has-feedback">
      ......
    </div>
    <div class="form-group has-error has-feedback">
      ......
    </div>
    </form>

从效果图中可以看出，图标都居右。在 Bootstrap 的小图标都是使用@font-face来制作（后面的内容中将会着重用一节内容来介绍）。而且必须在表单中添加了一个 span 元素：

    <span class="glyphiconglyphicon-warning-sign form-control-feedback"></span>

- `.help-block`：表单提示信息

#### 按钮

- `.btn`：基本按钮
- `.btn-default`：默认按钮
- `.btn-block`：块状按钮(width:100%)
- 活动状态：
    - `:hover`：悬浮状态
    - `:active`：点击状态
    - `:focus`：焦点状态

制作按钮除了使用`<button>`标签元素之外，还可以使用`<input type="submit">`和`<a>`标签<br/>
虽然在Bootstrap框架中使用任何标签元素都可以实现按钮风格，但个人并不建议这样使用，为了避免浏览器兼容性问题，个人强烈建议使用button或a标签来制作按钮。

    <button class="btn" type="button">基础按钮.btn</button>
    <button class="btn btn-default" type="button">默认按钮.btn-default</button>
    <button class="btn btn-primary" type="button">主要按钮.btn-primary</button>
    <button class="btn btn-success" type="button">成功按钮.btn-success</button>
    <button class="btn btn-info" type="button">信息按钮.btn-info</button>
    <button class="btn btn-warning" type="button">警告按钮.btn-warning</button>
    <button class="btn btn-danger" type="button">危险按钮.btn-danger</button>
    <button class="btn btn-link" type="button">链接按钮.btn-link</button>

在Bootstrap框架中，要禁用按钮有两种实现方式：

- 在标签中添加disabled属性
- 在元素标签中添加类名“disabled”

两者的主要区别是：

“.disabled”样式不会禁止按钮的默认行为，比如说提交和重置行为等。如果想要让这样的禁用按钮也能禁止按钮的默认行为，则需要通过JavaScript这样的语言来处理。对于`<a>`标签也存在类似问题，如果通过类名“.disable”来禁用按钮，其链接行为是无法禁止。而在元素标签中添加“disabled”属性的方法是可以禁止元素的默认行为的。

下面是两种方法的举例：

    <button class="btnbtn-primary btn-lgbtn-block" type="button" disabled="disabled">通过disabled属性禁用按钮</button>
    <button class="btnbtn-primary btn-block disabled" type="button">通过添加类名disabled禁用按钮</button>
    <button class="btnbtn-primary btn-smbtn-block" type="button">未禁用的按钮</button>

#### 图像

- `img-responsive`：响应式图片，主要针对于响应式设计
- `img-rounded`：圆角图片
- `img-circle`：圆形图片
- `img-thumbnail`：缩略图片

对icon设置一个默认样式，在Bootstrap框架中是通过给元素添加“glyphicon”类名来实现，然后通过伪元素“:before”的“content”属性调取对应的icon编码

在网页中使用图标也非常的简单，在任何内联元素上应用所对应的样式即可：

    <span class="glyphicon glyphicon-search"></span>
    <span class="glyphicon glyphicon-asterisk"></span>
    <span class="glyphicon glyphicon-plus"></span>
    <span class="glyphicon glyphicon-cloud"></span>

#### 网格系统

Bootstrap框架的网格系统工作原理如下：

1. 数据行(.row)必须包含在容器（.container）中，以便为其赋予合适的对齐方式和内距(padding)。如：

    <div class="container">
    <div class="row"></div>
    </div>

2. 在行(.row)中可以添加列(.column)，但列数之和不能超过平分的总列数，比如12。如：

    <div class="container">
    <div class="row">
      <div class="col-md-4"></div>
      <div class="col-md-8"></div>

3. 具体内容应当放置在列容器（column）之内，而且只有列（column）才可以作为行容器(.row)的直接子元素
4. 通过设置内距（padding）从而创建列与列之间的间距。然后通过为第一列和最后一列设置负值的外距（margin）来抵消内距(padding)的影响

列偏移只需要在列元素上添加类名 `col-md-offset-*` (其中星号代表要偏移的列组合数)，那么具有这个类名的列就会向右偏移。

列排序其实就是改变列的方向，就是改变左右浮动，并且设置浮动的距离。在Bootstrap框架的网格系统中是通过添加类名 `col-md-push-*` 和 `col-md-pull-*` (其中星号代表移动的列组合数)。

- `col-md-push-#`：向右浮动
- `col-md-pull-#`：向左浮动

#### 下拉菜单

官网示例：

    <div class="dropdown">
        <button class="btn btn-default dropdown-toggle" type="button" id="dropdownMenu1" data-toggle="dropdown">
            下拉菜单
            <span class="caret"></span>
        </button>
        <ul class="dropdown-menu" role="menu" aria-labelledby="dropdownMenu1">
           <li role="presentation"><a role="menuitem" tabindex="-1" href="#">下拉菜单项</a></li>
           …
           <li role="presentation" class="divider"></li>
           <li role="presentation"><a role="menuitem" tabindex="-1" href="#">下拉菜单项</a></li>
        </ul>
    </div>

下拉菜单使用方法：

在使用Bootstrap框架中的下拉菜单组件时，其结构运用的正确与否非常的重要，如果结构和类名未使用正确，直接影响组件是否能正常运用。我们来简单的看看：

1. 使用一个名为“dropdown”的容器包裹了整个下拉菜单元素，示例中为:

    <div class="dropdown"></div>

2. 使用了一个`<button>`按钮做为父菜单，并且定义类名“dropdown-toggle”和自定义“data-toggle”属性，且值必须和最外容器类名一致，此示例为:

    data-toggle="dropdown"

3. 下拉菜单项使用一个ul列表，并且定义一个类名为“dropdown-menu”，此示例为:

    <ul class="dropdown-menu">

- `.divider`：下拉分隔线
- `.dropdown-header`：下拉内容头部标题

下拉菜单相对于父容器右对齐，可以在 `dropdown-menu` 上添加一个 `pull-right` 或者 `dropdown-menu-right` 类名

菜单栏状态：

- `:hover` - 悬浮状态
- `:focus` - 焦点状态
- `.active` - 当前状态
- `.disabled` - 禁用状态

#### 按钮组

按钮组使用一个名为“btn-group”的容器，把多个按钮放到这个容器中。

#### 按钮工具栏

按钮工具栏，只需要将按钮组“btn-group”按组放在一个大的容器“btn-toolbar”中

嵌套分组，只需要把当初制作下拉菜单的 `dropdown` 的容器换成 `btn-group`，并且和普通的按钮放在同一级

- `.btn-group-vertical`：按钮组垂直显示

等分按钮在移动端上特别实用，整个按钮组宽度是容器的 100%，按钮组里的每个按钮平分整个容器宽度。<br/>
等分按钮也被称为自适应分组按钮，实现方法，只需要在按钮组“btn-group”上追加一个“btn-group-justified”类名

把“btn-group-justified”模拟成表格（display:table），而且把里面的按钮模拟成表格单元格（display:table-cell）

#### 按钮下拉菜单

向上弹起的下拉菜单（caret 方向朝上显示）：在“.btn-group”类上追加“dropup”类名（这也是做向上弹起下拉菜单要用的类名）

#### 导航

标签形导航栏是通过 `nav-tab` 样式来实现。在制作标签形导航时需要在原导航“nav”上追加此类名

假设我们想让“Home”项为当前选中项，只需要在其标签上添加类名“class="active"”即可：

    <ul class="nav nav-tabs">
        <li class="active"><a href="##">Home</a></li>
        …
    </ul>

- 选项卡还带有禁用状态，实现这样的效果，只需要在标签项上添加“class="disabled"
- 胶囊形导航通过类名 `nav-pills` 实现
- 垂直堆叠导航通过类名 `nav-stacked` 实现
- 导航栏分隔线 `class=nav-divider`
- 自适应导航使用类名 `nav-justified`

#### 导航加下拉菜单（二级导航）

在Bootstrap框架中制作二级导航，只需要将li当作父容器，使用类名“dropdown”，同时在li中嵌套另一个列表ul

#### 面包屑式导航

面包屑(Breadcrumb)一般用于导航，主要起的作用是告诉用户现在所处页面的位置(当前位置)，使用方法就是在 `<ol>` 或 `<ul>` 标签中加入类 `class="breadcrumb"`

#### 导航条

导航条(navbar) 和导航(nav) 区别：

- navbar 中有一个背景色
- navbar 可以是纯链接（类似nav），也可以是表单，还可以是表单和导航一起结合等多种形式

导航条使用方法：

- 第一步：首先在制作导航的列表(`<ul class=”nav”>`)基础上添加类名“navbar-nav”
- 第二步：在列表外部添加一个容器（div），并且使用类名“navbar”和“navbar-default”
- 通过“navbar-header”和“navbar-brand”在菜单前面添加标题
- 通过“nav-form”在导航条内添加表单，`navbar-left` 和 `navbar-right` 实现表单左浮动和右浮动

示例：

    <div class="navbar navbar-default" role="navigation">
         <ul class="nav navbar-nav">
    	 	<li class="active"><a href="##">首页</a></li>
            <li><a href="##">AAAAA</a></li>
            <li><a href="##">BBBBB</a></li>
            <li><a href="##">CCCCC</a></li>
            <li><a href="##">DDDDD</a></li>
    	 </ul>

导航条中还可以使用按钮、文本和链接：

- 导航条中的按钮navbar-btn
- 导航条中的文本navbar-text
- 导航条中的普通链接navbar-link

Bootstrap 框架提供了两种固定导航条的方式：

- .navbar-fixed-top：导航条固定在浏览器窗口顶部
- .navbar-fixed-bottom：导航条固定在浏览器窗口底部

固定导航条会遮住 body 内容，只需要修改 css：

    body {
    padding-top: 70px;/*有顶部固定导航条时设置*/
    padding-bottom: 70px;/*有底部固定导航条时设置*/
    }

还有一种办法，把导航条放在页面内容前面

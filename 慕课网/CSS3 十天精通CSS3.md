# CSS 十天精通CSS3

#### 边框 圆角效果 border-radius

实心上半圆，实现方法：把高度(height)设为宽度（width）的一半，并且只设置左上角和右上角的半径与元素的高度一致（大于也是可以的）。

    div{
        height:50px;/*是width的一半*/
        width:100px;
        background:#9da;
        border-radius:50px 50px 0 0;/*半径至少设置为height的值*/
        }

#### 边框阴影 box-shadow

- 使用方法：`box-shadow: X轴偏移量 Y轴偏移量 [阴影模糊半径] [阴影扩展半径] [阴影颜色] [投影方式];`
- 注意：inset 可以写在参数的第一个或最后一个，其它位置是无效的
- 添加多个阴影，只需用逗号隔开即可
- 阴影模糊半径：此参数可选，其值只能是为正值，如果其值为0时，表示阴影不具有模糊效果，其值越大阴影的边缘就越模糊
- 阴影扩展半径：此参数可选，其值可以是正负值，如果值为正，则整个阴影都延展扩大，反之值为负值时，则缩小
- X轴偏移量和Y轴偏移量值可以设置为负数

#### 边框应用图片 border-image

- 语法：`border-image:url(xxx.jpg) 70 70 70 70 repeat;`
- 数字为切割图片的宽度，单位为像素，但省略 px 也可以使用百分比，遵循顺时针的规律来分别设置
- 图片延伸方式，三个可选参数分别为：
    - round，平铺
    - repeat，重复
    - stretch，拉伸

#### 渐变色彩

CSS3 Gradient 分为线性渐变(linear) 和径向渐变(radial)

- 语法：`linear-gradient(to bottom, #fff, #999)`
- 第一个参数：指定渐变方向，可以用“角度”或“英文”来表示
    - to top
    - to right
    - to bottom
    - to left
    - to top left
    - to top right
- 第二个和第三个参数，表示颜色的起始点和结束点，可以有多个颜色值

#### 文字与字体 text-overflow & word-wrap

- `text-overflow: clip / ellipsis`
    - clip：表示 剪切
    - ellipsis：表示显示，省略标记
- `word-wrap: normal / break-word`
    - 表示控制连续文本换行
    - 表示内容将在边界内换行

#### 嵌入字体 @font-face

    @font-face {
        font-family : 字体名称;
        src : 字体文件在服务器上的相对或绝对路径;
    }

#### 文本阴影 text-shadow

- `text-shadow: X-Offset Y-Offset blur color;`
    - X-Offset：表示阴影的水平偏移距离，其值为正值时阴影向右偏移，反之向左偏移   
    - Y-Offset：是指阴影的垂直偏移距离，如果其值是正值时，阴影向下偏移，反之向上偏移
    - Blur：是指阴影的模糊程度，其值不能是负值，如果值越大，阴影越模糊，反之阴影越清晰，如果不需要阴影模糊可以将Blur值设置为0(blur注意要加px单位)
    - Color：是指阴影的颜色，其可以使用rgba色

#### 背景

- `background-origin ： border-box / padding-box / content-box;`
- 需要注意的是，如果背景不是no-repeat，这个属性无效，它会从边框开始显示

`background-clip` 用来将背景图片做适当的裁剪以适应实际需要。语法：

- `background-clip ： border-box / padding-box / content-box / no-clip`
- 参数分别表示从边框、或内填充，或者内容区域向外裁剪背景。no-clip表示不裁切，和参数border-box显示同样的效果
- backgroud-clip默认值为border-box

`background-size` 设置背景图片的大小，以长度值或百分比显示，还可以通过 cover 和 contain 队图片进行伸缩

- `background-size: auto / <长度值> / <百分比> / cover / contain`
    - auto：默认值，不改变背景图片的原始高度和宽度；
    - <长度值>：成对出现如200px 50px，将背景图片宽高依次设置为前面两个值，当设置一个值时，将其作为图片宽度值来等比缩放；
    - <百分比>：0％~100％之间的任何值，将背景图片宽高依次设置为所在元素宽高乘以前面百分比得出的数值，当设置一个值时同上；
    - cover：顾名思义为覆盖，即将背景图片等比缩放以填满整个容器；
    - contain：容纳，即将背景图片等比缩放至某一边紧贴容器边缘为止。

#### 使用渐变与伪类选择器制作导航分隔线

    /*使用伪元素制作导航列表项分隔线*/
    .nav li{background:linear-gradient(to bottom,#dd2926,#a82724,#dd2926) no-repeat right / 3px 15px;}
    /*删除第一项和最后一项导航分隔线*/
    .nav li:last-child{background:none;}

#### 选择器

- `:root`：根选择器
- `:not`：否定选择器
    - 注意，`:not`需要紧跟在元素名后面，中间不能有空格
- `:empty`：空选择器，用来选择没有任何内容的元素，这里没有内容指的是一点内容都没有，哪怕是一个空格
- `:target`：目标选择器，用来匹配文档(页面)的url的某个标志符的目标元素
- `::selection`：伪类元素选择器用来匹配突出显示的文本(用鼠标选择文本时的文本)
- `:read-only`：伪类选择器用来指定处于只读状态元素的样式。简单点理解就是，元素中设置了“readonly=’readonly’”
- `:read-write`：指定当元素处于非只读状态时的样式
- `::before`和`::after`这两个主要用来给元素的前面或后面插入内容，这两个常和"content"配合使用，使用的场景最多的就是清除浮动

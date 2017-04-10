# 玩转 Bootstrap（JS插件）

#### 一次性导入

    <!—导入jQuery版本库，因为Bootstrap的JavaScript插件依赖于jQuery -->
    <script src="http://libs.baidu.com/jquery/1.9.0/jquery.js"></script>
    <!—- 一次性导入所有Bootstrap的JavaScript插件（压缩版本） -->
    <script src="js/bootstrap.min.js"></script>

#### 单独导入

- 动画过渡（Transitions）:对应的插件文件“transition.js”
- 模态弹窗（Modal）:对应的插件文件“modal.js”
- 下拉菜单（Dropdown）：对应的插件文件“dropdown.js”
- 滚动侦测（Scrollspy）：对应的插件文件“scrollspy.js”
- 选项卡（Tab）：对应的插件文件“tab.js”
- 提示框（Tooltips）：对应的插件文件“tooltop.js”
- 弹出框（Popover）：对应的插件文件“popover.js”
- 警告框（Alert）：对应的插件文件“alert.js”
- 按钮（Buttons）：对应的插件文件“button.js”
- 折叠/手风琴（Collapse）：对应的插件文件“collapse.js”
- 图片轮播Carousel：对应的插件文件“carousel.js”
- 自动定位浮标Affix：对应的插件文件“affix.js”

#### 模态弹出窗

- 声明式触发方法
    - 自顶两个属性：`data-toggle` & `data-target`
    - 使用链接 `<a>` 元素触发，使用 `href` 替代 `data-target`
    - 建议统一使用 `data-target` 来触发模态弹出窗
    - 动画过渡效果，增加类名 `fade`
- JavaScript触发方法

JavaScript 触发的模态弹出窗，代码示例：

    $(function(){
      $(".btn").click(function(){
        $("#idName").modal();
      });
    });
    //参数
    $(function(){
      $(".btn").click(function(){
        $("#idName").modal({
            keyboard:false
            });
      });
    });

#### 下拉菜单 Dropdown

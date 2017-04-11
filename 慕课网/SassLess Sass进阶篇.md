# Sass进阶篇

#### `@for` 循环

`@for` 循环有两种方式：

    @for $i from <start> through <end>
    @for $i from <start> to <end>

- $i 表示变量
- start 表示起始值
- end 表示结束值
- 区别是关键字 through 表示包括 end 这个数，而 to 则不包括 end 这个数

#### `@each` 循环

`@each` 循环就是去遍历一个列表，然后从列表中取出对应的值。`@each` 循环指令的形式：

    @each $var in <list>

#### Sass 函数功能

- 字符串函数
- 数字函数
- 列表函数
- 颜色函数
- Introspection 函数
- 三元函数等

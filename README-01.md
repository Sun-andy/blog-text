# 《HTML入门笔记1》

1. HTML是谁发明的？

  HTML是由Tim Berners-Lee(李爵士)发明的。

2. HTML起手应该些什么？
Emmet感叹号
```html
<!DOCTYPE html>
<!--文档类型--> 
<html lang="zh-CN">
<!--html标签，lang最开始为en，改为中文-->
<head>
    <meta charset="UTF-8">
    <!--文件字符编码-->
    <meta name="viewport" content="width=device-width,initial-scale=1.0">
    <!--禁用缩放，兼容手机-->
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <!--告诉IE使用最新内核-->
    <title>你好</title>
    <!--标题-->
</head>
<body>
~~~~~~~~~~
</body>
</html>

```
3. 常用的表示章节的标签有哪些，分别是什么意思?

  常用章节标签有：h1~h6(标题)、section(章节)、article(文章)、p(段落)、header(头部)、footer(脚部)、main(主要内容)、aside(旁支内容)、div(划分)。
  
4. 全局属性有哪些？

全局属性有

* class
class属性用来对网页元素进行分类。如果不同元素的class属性值相同，就表示它们是一类的。
```
<p class="para"></p>
<!-- 为p分类，若class相同，则为同一类-->

<p class="p1 p2 p3"></p>
<!--一个网页元素有多个分类-->
```
* contenteditable 
contenteditable允许用户修改网页内容，该属性是枚举属性，不是布尔属性，规范的写法是最好带上属性值。
 ```
 <p contenteditable="true">
鼠标点击，本句内容可修改。
</p>

 ```
* id id属性是元素在网页内的唯一标识符。比如，网页可能包含多个标签，id属性可以指定每个标签的唯一标识符。

id属性的值必须是全局唯一的，同一个页面不能有两个相同的id属性。另外，id属性的值不得包含空格。
```
<p id="p1">  </p>
<p id="p2">  </p>
<p id="p3">  </p>

```
* style
style属性用来指定当前元素的 CSS 样式。
```
<p style="color: red;">hello</p>

```
* tabindex
tabindex用于网页tab切换网页元素。

i. 当值为-1时代表不能切换。

ii. 正数时按数的大小从小到大切换。

iii. 值为0代表最后的切换位。
```
<p tabindex="0"> ~~~ </p>

```
* title
title属性用来为元素添加附加说明。大多数浏览器中，鼠标悬浮在元素上面时，会将title属性值作为浮动提示，显示出来。
```
<div title="版权说明">
  <p>本站内容使用创意共享许可证，可以自由使用。</p>
</div>

```
5. 常用的内容标签有哪些，分别是什么意思?

常用的内容标签有：

* ol+li(ordered list+list item) 有序列表和列表项
* ul+li( unordered list+list item)无序列表和列表项
* dl+dt+dd(description list+term+detail)自定义列表
* pre   HTML不能多个连续的空格、tab、Enter并存，只会保留一个，pre是能够保留多个空格的标签
* hr  分割线
* br  换行
* a  链接
* em 和 strong 
  em是emphasis的意思，用于语气强调，强调部分会以斜体显示
  strong也用于强调，强调部分会以粗体显示
* code 用于代码，会以等宽字体显示，若有换行，则需要搭配pre
* quote 是用来定义一个短的引语，只包含存文本，或者内联元素
* blockquote  用来定义一段引语，但blockquote的子节点必须为块元素，而不能是文本或者内联元素

# CSS 基础
## 1.CSS语法
> css规则：选择器，以及一条或多条声明
```
selector {declaration1; declaration2; ... declarationN }
```
> 属性（property）是您希望设置的样式属性（style attribute）。每个属性有一个值。属性和值被冒号分开。
```
h1 {color:red; font-size:14px;}
```
### 选择器分组
```
h1,h2,h3,h4,h5,h6 {
  color: green;
  }
```
### 选择器继承
> 创建一个针对 p 的特殊规则，这样它就会摆脱父元素的规则
```
body  {
     font-family: Verdana, sans-serif;
     }

td, ul, ol, ul, li, dl, dt, dd  {
     font-family: Verdana, sans-serif;
     }

p  {
     font-family: Times, "Times New Roman", serif;
     }
```
### 派生选择器
```
li strong {
    font-style: italic;
    font-weight: normal;
  }
```
### id 类选择器
```
#red {color:red;}
#green {color:green;}

.center {text-align: center}

```
> 在现代布局中，id 选择器常常用于建立派生选择器。
```
#root p {
	font-style: italic;
	text-align: right;
	margin-top: 0.5em;
	}
```
### 属性选择器
> 围殴带有title属性的所有元素设置样式
```
[title]{
            color:red;
        }
```
> 为指定title属性值的所以元素设置样式
```
[title=W3School]
{
border:5px solid blue;
}
```
>为包含指定值的 title 属性的所有元素设置样式。适用于由空格分隔的属性值
```
[title~=hello] { color:red; }
```
>为带有包含指定值的 lang 属性的所有元素设置样式。适用于由连字符分隔的属性值
```
[lang|=en] { color:red; }
```
>[attribute^=value]	匹配属性值以指定值开头的每个元素
>[attribute$=value]	匹配属性值以指定值结尾的每个元素
>[attribute*=value]	匹配属性值中包含指定值的每个元素
>属性选择器在为不带有 class 或 id 的表单设置样式时特别有用
```
input[type="text"]
{
  width:150px;
  display:block;
  margin-bottom:10px;
  background-color:yellow;
  font-family: Verdana, Arial;
}

input[type="button"]
{
  width:120px;
  margin-left:35px;
  display:block;
  font-family: Verdana, Arial;
}
```
## 2.css样式
### css创建
> 外部样式表
```
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css" />
</head>
```
> 内部样式表
```
<head>
<style type="text/css">
  hr {color: sienna;}
  p {margin-left: 20px;}
  body {background-image: url("images/back40.gif");}
</style>
</head>
```
> 内联样式
```
<p style="color: sienna; margin-left: 20px">
This is a paragraph
</p>
```
> 优先级 内联样式>内部样式表>外部样式表
### css背景
> 背景色
```
p {background-color: gray;}
```
> 背景图片
```
body {background-image: url(/i/eg_bg_04.gif);}
```
> 背景重复 background-repeat
```
body
  {
  background-image: url(/i/eg_bg_03.gif);
  background-repeat: repeat-y;
  }
```
> 背景定位 background-position
```
body
  {
    background-image:url('/i/eg_bg_03.gif');
    background-repeat:no-repeat;
    background-position:center;
  }
```
> 背景关联 background-attachment
```
body
  {
  background-image:url(xxx.jpg);
  background-repeat:no-repeat;
  background-attachment:fixed
  }
```
### css文本
> 缩进文本  (可继承)
```
p {text-indent: 5em;}
```
> 水平对齐
```
text-align:center/left/right/justify/inherit
```
> 字间隔
```
p
  {
  word-spacing:25px;
  }
```
> 字符转换
```
text-transform:none/uppercase/lowercase/capipalize
```
> 文本修饰
```
text-decoration:none/underline/overline/line-through/blink
```
> 处理空白符
```
<p>This     paragraph has    many
    spaces           in it.</p>
    p {white-space: normal;}
```
### css字体
> 指定字体
```
body {font-family: sans-serif;}
```
> 字体风格
```
 {font-style:normal;}
 {font-style:italic;}
 {font-style:oblique;}
```
>字体大小 font-size
>字体加粗 font-weight
>字体变形   可以设定小型大写字母
```
p {font-variant:small-caps;}
```
### css链接
>链接的四种状态
```
a:link {color:#FF0000;}		 /* 未被访问的链接 */
a:visited {color:#00FF00;}	/* 已被访问的链接 */
a:hover {color:#FF00FF;}	            /* 鼠标指针移动到链接上 */
a:active {color:#0000FF;}	           /* 正在被点击的链接 */
```
### css列表
> 列表类型 list-style-type
```
ul {list-style-type:circle;}
ul {list-style-type:square;}
ol {list-style-type:upper-roman;}
ol {list-style-type:lower-alpha;}
```
> 列表项图像
```
ul li {list-style-image : url(xxx.gif)}
```
> 列表项位置
```
ul{list-style-position:inside;}
```
> 上面三项简写 ： {list-style:square inside url(xxx.gif)}
### css表格
> 表格边框
```
table, th, td{border: 1px solid blue;}
```
>折叠边框
```
table{ border-collapse:collapse;}
table,th, td{border: 1px solid black;}
```
>表格文本对齐  text-align水平对齐  vertical-align 垂直对齐
```
td
  {
  text-align:right;
  vertical-align:bottom;
  }
```
### css 轮廓
```
{
border:red solid thin;
outline:#00ff00 dotted thick;   /*color  style width*/
}
```
### css 盒模型
> 标准盒模型 在标准的盒子模型中，width指content部分的宽度

> IE盒模型 在IE盒子模型中，width表示content+padding+border这三个部分的宽度
```
  box-sizing: content-box 是W3C标准盒子模型  (默认)
  box-sizing: border-box 是IE盒子模型
```
> CSS 框模型 (Box Model) 规定了元素框处理元素内容(element)、内边距(padding)、边框(border) 和 外边距(margin) 的方式

> 外边距合并 (margin)
```
外边距合并指的是，当两个垂直外边距相遇时，它们将形成一个外边距。合并后的外边距的高度等于两个发生合并的外边距的高度中的较大者
```
### css 定位
> position 属性
```
{position:absolute}   /*绝对定位，相对于第一个父级定位*/
{position:fixed}      /*固定定位，相对于浏览器定位*/
{position:relative}   /*相对定位，对于自身定位*/
{position:static}     /*默认，没有定位*/
{position:inherit}    /*继承父元素的position属性*/
```
>定位元素移动
```
left top bottom right

z-index 设置元素的堆叠顺序
```
### css 浮动
> 浮动元素脱离文档流
```
{float:left/right;}
```
>设置伪类清除浮动

```
.clearfloat:after{
    display:block;
    clear:both;
    content:"";
    visibility:hidden;
    height:0}
.clearfloat{zoom:1}
```
>在结尾处添加空div标签clear:both

>父级div定义height
## 3.css选择器
### 元素选择器
```
div{color:red}
```
### 选择器分组
```
 h1,h2,h3{color:red}
```
### 类选择器
```
<div class='ccc'></div>
.ccc{color:red}
```
### ID选择器
```
<div id='ccc'></div>
#ccc{color:red}
```
###  后代选择器
```
<div id='ccc'><p class="c"></p></div>
#ccc .c{color:red}
```
### 子代选择器
>如果从右向左读，选择器 h1 > strong 可以解释为“选择作为 h1 元素子元素的所有 strong 元素”
```
    h1>strong{}
```
### 相邻兄弟选择器
>这个选择器读作：“选择紧接在 h1 元素后出现的段落，h1 和 p 元素拥有共同的父元素”
```
h1 + p {margin-top:50px;}
```
### 伪类
```
a:link {color: #FF0000}
a:visited {color: #00FF00}
a:hover {color: #FF00FF}
a:active {color: #0000FF}
```
### 伪元素
```
h1:after
  {
  content:url(logo.gif);
  }
```










# css 高级
## 1.css 三大特性
### 1.1 优先级
>!important > 行内样式>ID选择器 > 类选择器 > 标签 > 通配符 > 继承 > 浏览器默认属性
### 1.2 继承
> 继承即子类元素继承父类的样式，比如font-size,font-weight等f开头的css样式以及text-align,text-indent等t开头的样式以及我们常用的color
### 1.3 层叠
>层叠是css的一个特性，如果两个相同的属性作用于同一标签，它们会发生层叠。如果多个复合选择器，同时作用于我们的同一标签，优先级就不好计算了，就要计算权重，通过比较权重，来先出优先级最高的选择器
## 2.文本溢出
### 2.1 溢出属性（容器的）
>overflow:visible/hidden(隐藏)/sroll/auto(自动）/inherit
```
visible:默认值，内容不会被修剪，会出现在元素框之外；
hidden：内容会被修剪，并且其余内容是不可见的；
scroll：内容会被修剪，但是浏览器会显示滚动条，以便查看其余的内容;
auto：如果内容被修剪，则浏览器会显示滚动条，以便查看其他的内容;
inherit：规定应该从父元素继承overflow属性的值
```
### 2.2 空白空间
> white-space:normal/pre/nowrap/pre-wrap /pre-line /inherit
```
pre：用等宽字体显示预先格式化的文本，不合并文字间的空白距离，当文字超出边界时不换行。
nowrap:强制在同一行内显示所有文本，直到文本结束或者遭遇br对象；
normal：默认处理方式。
pre-wrap：用等宽字体显示预先格式化的文本，不合并文字间的空白距离，当文字碰到边界时发生换行。 (css2.1新增)
pre-line:保持文本的换行，不保留文字间的空白距离，当文字碰到边界时发生换行。 (css2.1新增)
inherit：规定应该从父元素继承White-space属性的值；(ie浏览器都不支持此属性值)
```
### 2.3 文本溢出
> text-overflow: clip/ellipsis
```
clip：不显示省略号（...），而是简单的裁切;
ellipsis：当对象内文本溢出时，显示省略标记
```
>配合使用
```
容器宽度：width：value；（px、%，都可以）
强制文本在一行内显示:white-space：nowrap;
溢出内容为隐藏：overflow：hidden；
溢出文本显示省略号： text-overflow：ellipsis;
```
## 3.元素分类
> 块状元素 /内联元素 /可变元素
### 3.1 块级元素
> 块状元素都可以定义自己的宽度和高度
```
div,dl,dt,dd,ol,ul,fieldset,（h1-h6）,p,form,hr,iframe,colgroup,col,table,tr,td
```
### 3.2 行内(内联)元素
>内联元素没有自己的形状，不能定义它的宽和高,它显示的宽度、高度只能根据所包含内容的高度和宽度来确定，它的最小内容单元也会呈现矩形形状
```
a,span,i,em,strong,b等修饰类型的元素
```
### 3.3 可变元素
> 需要根据上下文关系确定该元素是块元素或者内联元素
```
button - 按钮
del - 删除文本
iframe - inline frame
ins - 插入的文本
map - 图片区块(map)
object - object对象
script - 客户端脚本
```
### 3.4 元素类型的转换
>display:block/inline/inline-block/none/list-item/table-header-group/table-footer-group
```
Block块状显示：类似在元素后面添加换行符，也就是说其他元素不能在其后面并列显示。
inline内联显示：在元素后面删除换行符，多个元素可以在一行内并列显示。
当元素设置了float属性后，就相当于给该元素加了display:block;属性；
Inline-block行内块元素显示：元素的内容以块状显示，行内的其他元素显示在同一行。（只有这一个元素类型支持vertical-align属性）img,input。
none 此元素不会被显示。
list-item:将元素转换成列表。li的默认类型
```
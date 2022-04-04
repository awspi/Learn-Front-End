# CSS

CSS的出现是为了美化HTML的，并且让结构(HTML)与样式(CSS)分离;

- 美化方式一:为HTML添加各种各样的样式，比如颜色、字体、大小、下划线等等; 
- 美化方式二:对HTML进行布局，按照某种结构显示(CSS进行布局 – 浮动、flex、grid);

## CSS规则

`属性名: 属性值`

## 三种编写规则

* 内联样式



* 内部样式



* 外部样式

  * link

  * @import 

  ```html
  <link rel="stylesheet" href="./css/style.css">
  ```

  

**@import**

可以在style元素或者CSS文件中使用@import导入其他的CSS文件

## 注释

`/* */`



## 文档

- **W3C**:https://www.w3.org/TR/?tag=css
- **MDN**:https://developer.mozilla.org/zh-CN/docs/Web/CSS/Reference#%E5%85%B3%E9%94%AE%E5%AD%97%E7%B4%A2%E5%BC%95

## 常见的CSS

* **font-size(fz)**
* **color**
* **background-color(bgc)**
* **width**
* **height**

```html
<head>
	<style>
    .title {
      font-size: 24px;
      color: chocolate;
      background-color:aqua;

      width: 200px;
      height: 200px;
    }
  </style>
</head>
<body>
  <div class="title">Hello World</div>
</body>
```

### 





## 核心CSS

### ① 定位(Position)和布局(Layout)

- ​	position
- ​	top/bottom/left/right
- ​	z-index
- ​	float/clear
- ​	flexbox
  - flex-direction
  - justify-content
  - align-items
  - 等等...

### ② 展示(Display)和可见(Visibility)

- ​	display
- ​	opacity
- ​	visibility

### ③ 盒子模型（Box Model）顺序

- ​	margin
- ​	box-shadow
- ​	border
- ​	border-radius
- ​	width/height
- ​	padding

### ④ 背景设置（Background）

- ​	background

### ⑤ 字体（Font）、文本（Text）

- ​	font-family/font-size/font-weight/font-style
- ​	line-height
- ​	text-align/text-transform
- ​	color

### ⑥ 其他属性（Other Property）

- ​	overflow
- ​	clip
- ​	cursor
- ​	transform
- ​	animation、transition
- ​	white-space



## CSS属性 - 文本

### **text-decoration**(了解)

用于设置文字的装饰线

有如下常见取值: 

- **none**:无任何装饰线
  - 可以去除a元素默认的下划线
-  **underline**:下划线
-  **overline**:上划线
-  **line-through**:中划线(删除线)

*a元素有下划线的本质是被添加了text-decoration属性*

### text-transform

用于设置文字的大小写转换

 text-transform有几个常见的值:

- **capitalize**:(使...首字母大写)将每个单词的首字符变为大写 
- **uppercase**:(大写字母)将每个单词的所有字符变为大写
- **lowercase**:(小写字母)将每个单词的所有字符变为小写
- **none**:没有任何影响

实际开发中用JavaScript代码转化的更多

### text-indent

用于设置第一行内容的缩进

text-indent: 2em; 是缩进2个文字

**em**:相对字体的大小

### text-align(重要)

直接翻译过来设置文本的对齐方式

**定义行内内容(例如文字)如何相对它的块父元素对齐**

只对行内级(inline-level)元素有效

常用值

- **left**:左对齐
- **right**:右对齐
- **center**:正中间显示 
- **justify**:两端对齐

![text-align](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/text-align.png)

### letter-word-spacing

分别用于设置字母、单词之间的间距

## CSS属性 - 字体

### font-size(重要)

常用的设置

* **具体数值+单位**

  * 比如100px
  * 也可以使用em单位(不推荐):1em代表100%，2em代表200%，0.5em代表50%

*  **百分比(用的时候查文档)** 

  * 基于父元素的font-size计算，比如50%表示等于父元素font-size的一半

  ```html
  /* 字体设置的方式一: px */
  /* font-size: 50px; */
  /* 了解: em -> 父元素的字体的尺寸 */
  
  /* 字体设置的方式二: em */
  /* font-size: 2em; */
  
  /* 字体设置的方式三: 百分比% */
  ```

  



### font-family(重要)

**一般仅设置一次**

* 用于设置**文字的字体名称** 
  * 可以设置1个或者多个字体名称;
  * 浏览器会选择列表中第一个该计算机上有安装的字体; 
  * 或者是通过 @font-face 指定的可以直接下载的字体。




一般单独放在css文件里引入

```css
body {
  font-family: "Microsoft YaHei", "Heiti SC", tahoma, arial, "Hiragino Sans GB", "\5B8B\4F53", sans-serif;
}
```



### font-weight(重要)

用于设置文字的粗细(重量)

**常见的取值**:

- **100 | 200 | 300 | 400 | 500 | 600 | 700 | 800 | 900** 
  - 每一个数字表示一个重量 

**normal**:等于400

**bold**:等于700

*strong、b、h1~h6等标签的font-weight默认就是bold*

### font-style

用于设置文字的常规、斜体显示

- **normal**:常规显示
- **italic**(斜体):用字体的斜体显示(通常会有专门的字体)
- **oblique**(倾斜):文本倾斜显示(仅仅是让文字倾斜)

*em、i、cite、address、var、dfn等元素的font-style默认就是italic*



### font-varient

可以影响小写字母的显示形式

- **normal**:常规显示
- **small-caps**:将小写字母替换为缩小过的大写字母
  * 小写字母以大写显示, 但是高度保持小写的高度




### line-height(常用)

用于设置文本的行高

**行高:**简单理解为一行文字所占据的高度

**行高**:两个基线(baseline)距离

* 一行文本 -> line-height
* 行高 - 文本高度  = 行距

![行高](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/行高.png)



**假设div中只有一行文字，如何<u>让这行文字在div内部垂直居中**</u>

**只限于文字**,让`line-height=height`

```html
 <style>
    .box {
      height: 100px;
      background-color: #f00;
      color: #fff;

      line-height: 100px;
    }
  </style>
</head>
<body>
  
  <div class="box">我是div元素</div>

</body>
```



### font缩写属性

font 属性可以用来作为` font-style, font-variant, font-weight, font-size, line-height 和 font-family` 属性的简写;

 **规则**:

- font-style、font-variant、font-weight可以随意调换顺序，也可以省略
- /line-height可以省略，如果不省略，必须跟在font-size后面
- **font-size、font-family不可以调换顺序，不可以省略**

```css
 /* 1.5的行高是相对于font-size的 */
font: italic small-caps 700 30px/1.5 serif;
```


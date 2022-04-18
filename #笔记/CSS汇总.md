# CSS汇总



# CSS基础

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

### **text-decoration**

用于设置文字的装饰线

有如下常见取值: 

- **none**:无任何装饰线
  - 可以去除a元素默认的下划线
- **underline**:下划线
- **overline**:上划线
- **line-through**:中划线(删除线)

*a元素有下划线的本质是被添加了text-decoration属性*

### text-transform		

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

### ‼️text-align(重要)

**设置文本的对齐方式**

**定义行内内容(例如文字)如何相对它的块父元素对齐**

只对**块级(block-level)元素有效**‼️

行内级元素: 包括<u>行内非替换元素</u>**span/a** <u>行内替换元素*</u>*img/input/inline-block**

- 行内级元素设置`display: block;`

```html
.text1{
display: block;
text-align: center;
}
.text2{
text-align: center;
}
 <span class="text1">123</span>
 <div class="text2">111</div>
```



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

* **百分比(用的时候查文档)** 

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

- **normal**:等于400
- <u>**bold**:等于700</u>

*strong、b、h1~h6等标签的font-weight默认就是bold*

### font-style

用于设置文字的常规、斜体显示

- **normal**:常规显示
- **<u>italic</u>**(斜体):用字体的斜体显示(通常会有专门的字体)
- **oblique**(倾斜):文本倾斜显示(仅仅是让文字倾斜)

*em、i、cite、address、var、dfn等元素的font-style默认就是italic*



### font-varient

可以**影响小写字母**的显示形式

- **normal**:常规显示
- **small-caps**:将小写字母替换为缩小过的大写字母
  * 小写字母以大写显示, 但是高度保持小写的高度




### line-height(常用)‼️

**用于设置文本的行高** 

撑起**块级元素**的高度

**行高:**简单理解为一行文字所占据的高度

**行高**:两个基线(baseline)距离

* 一行文本 -> line-height
* 行高 - 文本高度  = 行距

![行高](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/行高.png)



**假设div中只有一行文字，如何让这行文字在div内部垂直居中**

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



## CSS选择

###  统配选择器

**通用选择器**

`*{}`

所有的元素都会被选中;

**一般用来给所有元素作一些通用性的设置**

*浏览器有时候会对一些元素做一些默认的设置,但是我们不需要,为了避免混乱,就对这些元素全部进行重置*

- 比如内边距、外边距;
- 比如重置一些内容;

**效率比较低(**浏览器遍历,但是有的用不到)，尽量不要使用;

```css
* {
  font-size: 30px;
  background-color: #f00;
}
/* 更推荐的做法 */
body, p, div, h2, span {
  margin: 0;
  padding: 0;
}
```



###  简单选择器(重要)‼️

简单选择器是开发中用的最多的选择器

- **元素选择器(type selectors), 使用元素的名称;**
- **类选择器(class selectors), 使用`.`类名**
- **id选择器(id selectors), 使用 `#id`;**

```html
<style>
  div {
    color: red;
  }

  .box {
    color: blue;
  }

  #home {
    color: green;
  }
</style>
<body>
  <div>我是div1</div>
  <div class="box">我是div2</div>
  <div id="home">我是div3</div>
</body>
```

- 在**同一个HTML文档中, id不要重复, 应该是唯一**
  - id值如果由多个单词组成，单词之间可以用中划线-、下划线_连接，也可以使用驼峰标识
  - 最好不要用标签名作为id值

```html
<!-- class/id的名称比较复杂 使用 - 或 _ -->
<div class="box one"></div>
<div class="box-one box-first"></div>
<div class="box_one box_first"></div>
<!-- <div class="JS常用 小驼峰boxOne 大驼峰BoxFirst"></div> -->
```



### 属性选择器

- 拥有某一个属性 **[att]**
- 属性等于某个值 **[att=val]**

```html
<style>
  [title] {
    color: red;
  }

  [title=div] {
    background-color: blue;
  }
</style>

<body>
<div>我是div元素</div>
  <div title="div">我也是div元素</div>
  <p>我是p元素</p>
  <h2 title="h2">我是h2元素</h2>
</body>
```



### 后代选择器(重要)‼️

- 后代选择器一: 所有的后代(**直接/间接的后代**)
  - 选择器之间以**空格**分割

![后代选择器](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/后代选择器.png)

- 后代选择器二: **直接子代选择器**(必须是**直接子代**)
  - 选择器之间以 **>** 分割;

```html
<style>
/* 后代选择器 */
.home span {
color: red;
font-size: 30px;
}

/* .home的子代的span元素设置一个背景 */
.home > span {
background-color: green;
}
</style>

  <div class="home">
    <span>啦啦啦啦</span>  
    <div class="box">
      <p>我是p元素</p>
      <span class="home-item">呵呵呵呵</span>
    </div>

    <div class="content">
      <div class="desc">
        <p>
          <span class="home-item">哈哈哈哈</span>
        </p>
      </div>
    </div>
  </div>
```





### 兄弟选择器

- 兄弟选择器一:**相邻**兄弟选择器 **+**
  - 使用符号 `+`连接
  - ` .box + .content {}`
- 兄弟选择器二: **普遍**兄弟选择器 **~**
  - 使用符号 `~` 连接
  - `.box ~ div{}`

```html
<style>
    .box + .content {
      color: red;
    }

    .box ~ div {
      font-size: 30px;
    }
  </style>
</head>
<body>
  
  <div class="home">
    <div>叽叽叽叽</div>
    <div class="box">呵呵呵呵</div>
    <div class="content">哈哈哈哈</div>
    <div>嘻嘻嘻嘻</div>
    <div>嘿嘿嘿嘿</div>
    <p>我是p元素</p>
  </div>

</body>
```



### 选择器组(重要)‼️

- **交集选择器**:需要同时符合两个选择器条件
  - **两个选择器紧密连接**


在开发中通常为了**精准的选择某一个元素**

```html
  <style>
    div.box {
      color: red;
      font-size: 30px;
    }
    .item.item1{
      color:green;
    }
  </style>
<body>
  
  <div class="box">我是div元素</div>
  <p class="box">我是p元素</p>
  <div class="item item1">item1</div>

</body>
```



- **并集选择器**: 符合一个选择器条件即可
  - **两个选择器以`,`号分割**


在开发中通常为了**给多个元素设置相同的样式**

```html
 <style>
    body, p, h1, h2 {
      color: red;
      font-size: 40px;
    }
  </style>
<body>

  <p>我是p元素</p>
  <h1>我是h1元素</h1>

</body>
```



### 伪类

Pseudo-classes

伪类是**选择器的一种，它用于选择处于特定状态的元素**

**常见的伪类有**

- **动态伪类**

  - `:link`、`:visited`、**:hover**、`:active`、:focus

- **目标伪类**

  - :target

- **语言伪类**

  - :lang()

- **元素状态伪类**

  - :enabled、:disabled、:checked

- **结构伪类**

  - :nth-child( )、:nth-last-child( )、:nth-of-type( )、:nth-last-

    of-type( )

  - :first-child、:last-child、:first-of-type、:last-of-type

  - ;root、:only-child、:only-of-type、:empty

- **否定伪类**

  - :not()

*https://developer.mozilla.org/zh-CN/docs/Web/CSS/Pseudo-classes*

#### **动态伪类**

* 使用举例
  * a:link 未访问的链接
  * a:visited 已访问的链接
  * **a:hover 鼠标挪动到链接上(重要)**‼️
  * a:active 激活的链接(鼠标在链接上长按住未松开)
  * `:focus` 指当前拥有输入焦点的元素

- **使用注意**
  - `**:hover`必须放在:link和`:visited`后面才能完全生效**
  - :active必须放在:hover后面才能完全生效
  - **所以建议的编写顺序**是`:link`、`:visited`、`:focus`、`:hover`、`:active` 
    - lv f ha

```HTML
<style>
    /* a元素的链接从来没有被访问过 */
    a:link {
      color: red;
    }

    /* a元素被访问过了颜色 */
    a:visited {
      color: green;
    }

    /* a/input元素聚焦(获取焦点) */
    a:focus {
      color: yellow;
    }

    /* a元素鼠标放到上面 */
    a:hover {
      color: blue;
    }

    /* 点下去了, 但是还没有松手 */
    a:active {
      color: purple;
    }

    /* 所有的状态下同样的样式 */
    a {
      color: orange;
    }
  </style>
<body>
  
  <a href="http://www.mi.com">小米</a>
  <a href="http://www.baidu.com">百度一下</a>

  <input type="text">

  <div>我是div元素</div>

</body>
```

*除了a元素，:hover、:active也能用在其他元素上*

直接给**元素**设置样式，相当于给**元素的所有动态伪类**都设置了

#### 伪元素

**常用的伪元素有**

- :first-line、`::first-line` (了解)
  - ::first-line可以针对首行文本设置属性
  - ::first-letter可以针对首字母设置属性
- :first-letter、`::first-letter`(了解)



- **:before**、`::before` **(常用)**‼️

- **:after**、`::after` **(常用)**‼️

  - 用来在一个元素的内容**之前或之后插入其他内容(可以是文字、图片)**

    - 常通过 **content 属性**来为一个**行内级元素**添加修饰性的内容。

      - **不能将`content:""`省略**
      - **只能用于行内级**,块级可以设置display:inline-block;

      

为了区分伪元素和伪类，建议**伪元素使用2个冒号**，比如::first-line

```html
      <style>
      .box::first-line {
      font-size: 30px;
      color: orange;
    }

    .box::first-letter {
      font-size: 50px;
      color: blue;
    }
  </style>
  <div class="box">
    <span class="keyword">雁门关，别名西陉关 ，坐落于我国山西省忻</span>州市代县以北约成员国20千米的雁门山。它是长城上的一个关键大关，与宁武关、偏关并称之为“外三关”。坐落于偏关县大河上，辖四侧墙，总长度数百公里。迄今仍有30千米储存完好无损，所有用砖遮盖，沿堤岸耸立，十分壮阔。“边关丁宁岩，山连紫塞，地控大河北，鑫城携手共进强。”这也是前人对偏关的赞扬。早在春秋战国时代，这儿便是赵武灵王攻克胡林的竞技场。唐朝名将在关东建有九龙庙，宋代建有魏镇、杨三关。现有的关城始建明洪武二十三年，是重点学科文物古迹。
  </div>
  	
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .before {
      color: red;
    }

    .after {
      color: blue;
    }

    /* 伪元素 */
    .item::before {
      content: "321";
      color: orange;
      font-size: 20px;
    }

    .item::after {
      /* content: "cba"; */
      content: url("../images/hot_icon.svg");
      color: green;
      font-size: 20px;

      /* 位置不是很好看(以后) */
      position: relative; /* 相对定位 */
      left: 5px;
      top: 2px;
    }

    /* .new::after {
      content: url("../images/new_icon.svg");
    } */

    /* 额外的补充 */
    /* ::after是一个行内级元素 */
    .box5::after {
      /* 使用伪元素的过程中, 不要将content省略 */
      content: "";

      display: inline-block;
      width: 8px;
      height: 8px;
      background-color: #f00;
    }
  </style>
</head>
<body>
  
  <div class="box">
    <span class="before">123</span>
    我是div元素
    <span class="after">abc</span>
  </div>

  <div class="box2">
    <span class="before">123</span>
    我是box2
    <span class="after">abc</span>
  </div>

  <!-- 伪元素方案 -->
<!-- 直接在要加的class后面加上 item -->
  <div class="box3 item">我是box3</div>
  <div class="box4 item">我是box4</div>

  <!-- 伪元素的补充 -->
  <div class="box5">我是box5</div>

</body>
</html>
```



#### 结构伪类

**:nth-child**

-  **:nth-child(1)**
   - 是父元素中的第1个子元素
-  **:nth-child(2n)** n代表任意正整数和0
   - **是父元素中的第偶数个子元素(第2、4、6、8......个)** 
   - 跟:nth-child(**even**)同义 even偶数
-  **:nth-child(2n + 1)** n代表任意正整数和0
   - 是父元素中的**第奇数个子元素(第1、3、5、7......个)** 
   - 跟:nth-child(**odd**)同义
-  **nth-child(-n + 2)**代表前2个子元素



 **:nth-last-child( )**

:nth-last-child()的语法跟:nth-child()类似<u>，不同点是:nth-last-child()**从最后一个子元素开始往前计数**</u> 

- :nth-last-child(1)，代表倒数第一个子元素
- **:nth-last-child(-n + 2)，代表最后2个子元素**



**:nth-of-type()**用法跟**:nth-child()**类似

- 不同点是:nth-of-<u>type()</u>计数时**只计算同种类型**的元素 不是的会跳过,不计数

- (排除所有的干扰项)

  

**:nth-last-of-type()**用法跟**:nth-of-type()**类似

- 不同点是:nth-last-of-type()**从最后一个这种类型的子元素开始**往前计数

```html
  <style>
    /* 需求: 选择box中的div元素, 并且是第三个子元素 */
    .box > div:nth-child(3) {
      color: red;
    }
    
    /* 需求: 直接选取box下的第三个子元素,不论是什么元素 */
    .box > :nth-child(3) {
      color: red;
    }

    /* 需求: 选择box中的第三个div元素(排除所有的干扰项) */
    /* 元素:nth-of-type, 只计算符合我元素类型的数量的元素 */
    .box > div:nth-of-type(3) {
      color: blue;
    }
  </style>
  
    <div class="box">
    <div>我是列表1</div>
    <p>我是p元素</p>
    <span>我是span1</span>
    <span>我是span2</span>
    <span>我是span3</span>
    <span>我是span4</span>
    <div>我是列表2</div>
    <div>我是列表3</div>
    </div>
```



**其他常见的伪类(了解):**

- **`:first-child`**，等同于:nth-child(1)
- **`:last-child`**，等同于:nth-last-child(1)
- `:first-of-type`，等同于:nth-of-type(1)
- `:last-of-type`，等同于:nth-last-of-type(1)
- `:only-child`，是父元素中唯一的子元素
- `:only-of-type`，是父元素中唯一的这种类型的子元素

下面的伪类偶尔会使用:

- `:root` 根元素，就是HTML元素 
- **`:empty` 代表里面完全空白的元素**



#### 否定伪类

:not()的格式是**:not(x)**

- x是一个**简单选择器** 
- 元素选择器、通用选择器、属性选择器、类选择器、id选择器、伪类(除否定伪类)

 :not(x)表示除x以外的元素

```html
		.box :not(.why) {
      color: blue;
    }
    <div class="box">
    <div class="item">列表内容1</div>
    <div class="item">列表内容2</div>
    <div class="why">列表内容3</div>
    <div class="item">列表内容4</div>
    <div class="item">列表内容5</div>
    <div>列表内容5</div>
    <div>列表内容5</div>
    <div>列表内容5</div>
  </div>
```



# CSS属性的特性

## CSS属性的继承

- CSS的某些属性具有继承性(**Inherited**):
- 如果一个属性具备继承性, 那么在该元素上设置后, 它的**后代元素都可以继承这个属性;**
- 当然, 如果后代元素自己有设置该属性, 那么**优先使用后代元素自己的属性(不管继承过来的属性权重多高);**

**一个属性是否具有继承性**

- 常见的<u>font-size/font-family/font-weight/line-height/color/text-align</u>都具有继承性;
  - **文本字体相关的基本都可以继承**

- 这些不用刻意去记, 用的多自然就记住了;
- 查MDN文档
- 调试工具



![继承属性](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/继承属性.png)

**继承过来的是计算值, 而不是设置值**

```html
  <style>
    .box {
      color: red;
      /* font-size: 30px; */
      /* 相对于自身字体(父元素的字体) */
      /* 浏览器 16px */
      font-size: 2em;/* 32px */
    }

  </style>
</head>
<body>
  
  <div class="box">
    box本身的内容  <!-- 32px-->
    <p>我是p元素</p>  <!-- /* 不是又2em变成64px .而是box计算后的32px */ -->
  </div>
```

![继承属性2](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/继承属性2.png)



**强制继承**  `border: inherit;`

```html
<style>
    .box {
      color: red;

      border: 2px solid purple;
    }

    .box p {
      /* 强制继承 很少用 */
      border: inherit;
    }
  </style>
</head>
<body>
  
  <div class="box">
    <p>我是p元素</p>
    <h1>我是h1元素</h1>
  </div>
```



## CSS属性的层叠

**什么是层叠**

- 对于一个元素来说, **相同一个属性我们可以通过不同的选择器给它进行多次设置;**
- 那么属性会被**一层层覆盖上去;**
- 但是**最终只有一个**会生效;

**那么多个样式属性覆盖上去, 哪一个会生效呢?**

- 判断一: **选择器的权重,** 权重大的生效, 根据权重可以判断出优先级;
- 判断二: **先后顺序**, 权重相同时, 后面设置的生效;

#### 选择器的权重

- !important:**10000**
- 内联样式:**1000**
- id选择器:**100**
- 类(伪类)选择器、属性选择器、伪类:**10** 
- 元素选择器、伪元素:**1**
- 通配符:**0**

![选择器权重](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/选择器权重.png)



## CSS属性的类型

### HTML元素的类型

*div是块级元素会独占一行, span是行内级元素会在同一行显示.*

- 到底什么是**块级元素(block)**, 什么是**行内级元素(inline)**呢?

**HTML定义元素类型的思路:**

- HTML元素有很多, 比如h元素/p元素/div元素/span元素/img元素/a元素等等;
- **当我们把这个元素放到页面上时, 这个元素到底占据页面中一行多大的空间呢?**
  - 为什么我们这里只说一行呢? 因为**垂直方向的高度通常是内容决定的**;(text-height)
  - 比如一个h1元素的标题, 我们必然是希望它独占一行的, 其他的内容不应该和我的标题放在一起;
  - 比如一个p元素的段落, 必然也应该独占一行, 其他的内容不应该和我的段落放在一起;
  - 而类似于img/span/a元素, 通常是对内容的某一个细节的特殊描述, 没有必要独占一行;

所以, 为了区分哪些元素需要独占一行, 哪些元素不需要独占一行, HTML将元素区分(本质是通过CSS的)成了两类:

- **块级元素(block-level elements): 独占父元素的一行**
- **行内级元素(inline-level elements):多个行内级元素可以在父元素的同一行中显示**

### **通过CSS修改元素类型**

但是事实上元素没有本质的区别:
**div之所以是块级元素仅仅是因为浏览器默认设置了display:block属性而已;**

```html
  <style>
    /* 10 */
    .box {
      height: 100px;
      background-color: #f00;
      color: #fff;

      /* 修改div元素的特性: 层叠 */
      display: inline;
    }

    span {
      background-color: #0f0;
      display: block;
    }
  </style>
<body>
  <div class="box">我是div元素</div>
  <a href="#">百度一下</a>
  <span>我是span元素</span>
  <a href="#">百度一下</a>
</body>
```



## display属性

display属性，能修改元素的显示类型，有4个常用值

- `block`:让元素显示为块级元素
  - 独占一行,**可以设置宽度和高度**
- `inline`:让元素显示为行内级元素
  - 和其他行内级元素同一行显示,**不能设置宽高**
- `inline-block`:让元素同时具备行内级、块级元素的特征
- `none`:**隐藏元素**

- `flex`

### ‼️display值的特性(重要)

**`block`块级元素**

- **独占父元素的一行**
- **可以设置宽高**
- 高度默认由内容决定

**`inline-block`行内块级元素**

- 跟其他行内级元素在**同一行显示**

- **可以设置宽高**

  - 对外来说，它是一个行内级元素(同行显示)
  - 对内来说，它是一个块级元素(可以设置宽高)的行内元素

  

**`inline`行内级元素**

- 跟其他行内级元素**在同一行显示**;
- **不可以设置宽高;**
- 宽高都由内容决定;



![display值的特性](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/display值的特性.png)

```html
  <!-- 补充:  -->
  <!-- img元素: inline - replaced -> 行内替换元素 -->
  <!-- 行内替换元素: 
    1> 和其他的行内级元素在同一行显示
    2> 可以设置宽度和高度 
  -->
```



### 编写HTML元素的注意事项

**块级元素、inline-block元素**

- 一般情况下，可以包含其他任何元素(比如块级元素、行内级元素、inline-block元素
- 特殊情况，**p元素不能包含其他块级元素**,h1-6等都不适合包含块级元素

**行内级元素(比如a、span、strong等)** 

- 一般情况下，**只能包含行内级元素**



## 元素的隐藏

- 方法一: **`display`**设置为`none`
  - 元素不显示出来, 并且也不占据位置, **不占据任何空间(**和不存在一样);
- 方法二: **`visibility`**设置为`hidden`
  - 设置为`hidden`, 虽然元素不可见, 但是**会占据元素应该占据的空间**;
  - 默认为`visible`, 元素是可见的;

```css
    .box {
      display: none;
    }

    .content {
      visibility: hidden;
    }
```

- 方法三: **`rgba`**设置颜色, 将a的值设置为0 rgba(0,0,0,0) **占据空间**
  - `rgba`的a设置的是alpha值, **可以设置透明**;
  - **`color`影响子元素**
  - **`background-color`不影响子元素**
- 方法四: **`opacity`**设置透明度, 设置为0   **占据空间**
  - 设置整个元素的透明度, **会影响所有的子元素都有一定的透明度**

```css
    .box1 {
      /* 不是很推荐 */
      /* color: #ff000088; */
      
      /* 推荐下面的写法 a -> alpha 0~1 */
      /* color: rgba(255, 0, 0, 0.5); */

      /* 通过颜色来隐藏 */
      /* color: rgba(0, 0, 0, 0) */

      /* 通过背景颜色透明度来隐藏 */
      /* background-color: rgba(0, 0, 0, 0); */
      background-color: transparent; /* rgba(0,0,0,0) */
    }

    /* opacity: 设置透明度, 并且会携带所有的子元素都有一定的透明度 */
    .box2 {
      opacity: 0.5;
    }op
```



## overflow属性

**overflow用于控制内容溢出时的行为**

- `visible`:溢出的内容照样可见
- `hidden`:溢出的内容直接裁剪
- `scroll`:溢出的内容被裁剪，但可以通过滚动机制查看
  - 会一直显示滚动条区域，滚动条区域占用的空间属于width、height
- **`auto`:自动根据内容是否溢出来决定是否提供滚动机制**

```css
    .box {
      width: 300px;
      height: 100px;
      background-color: #f00;

      /* overflow: visible */
      overflow: auto;
    }
```



## CSS样式不生效原因分析

- 选择器的**优先级**太低
- 选择器**没选中**对应的元素
- CSS属性的使用形式不对
  - 元素**不支持此CSS属性**，比如span默认是不支持width和height的
  - **浏览器不支持**此CSS属性，比如旧版本的浏览器不支持一些css module3的某些属性
  - **被同类型的CSS属性覆盖**，比如font覆盖font-size

**充分利用浏览器的开发者工具进行调试(增加、修改样式)、查错**



# CSS设置背景

## background-image

- background-image**用于设置元素的背景图片**
  - **会盖在**(不是覆盖)background-color的上面 

- 如果设置了**多张图片**
  - 设置的**第一张图片将显示在最上面，其他图片按顺序层叠在下面**

**如果设置了背景图片后，元素没有具体的宽高，背景图片是不会显示出来的**

```css
 background-image: url(../images/kobe01.jpg), url(../images/kobe02.png);
```



## background-repeat 

background-repeat用于**设置背景图片是否要平铺**

常见的设值有

- `repeat`:平铺
- `no-repeat`:不平铺
- `repeat-x`:只在水平方向平铺
- `repeat-y`:只在垂直平方向平铺

```
background-repeat: no-repeat;
```



## background-size

 background-size**用于设置背景图片的大小**

- auto:默认值, 以背景图本身大小显示
- cover:缩放背景图，**以完全覆盖铺满元素**,可能背景图片部分看不见
- contain:缩放背景图，**宽度或者高度铺满元素**，但是图片**保持宽高比**
- <percentage>:百分比，相对于背景区(background positioning area)
- length:具体的大小，比如100px

```css
<bg-size>#where 
<bg-size> = [ <length-percentage> | auto ]{1,2} | cover | contain
```

## background-position

background-position用于设置背景图片在水平、垂直方向上的具体位置 

- 可以设置具体的数值 比如 20px 30px;
- **水平方向**还可以设值:left、center、right
- **垂直方向**还可以设值:top、centebr、bottom
- 如果**只设置了1个方向，另一个方向默认是center**

![background-position](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/background-position.png)

```css
.box {
  height: 489px;
  background-color: #f00;

  background-image: url(../images/mhxy.jpg);
  background-position: center;
  background-position: 30px 40px;
}
```

## background-attachment

 **background-attachment决定背景图像的位置是在<u>视口</u>内固定，或者随着包含它的区块滚动。**(用的不多)

 可以设置以下3个值

- scroll:表示背景**相对于元素本身固定**， 而不是随着它的内容滚动
- local:表示背景**相对于元素的内容固定**。如果一个元素拥有滚动机制，背景将会**随着元素的内容滚动.** 
- fixed:表示背景**相对于浏览器视口固定**。即使一个元素拥有滚动机制，背景**也不会随着元素的内容滚动。**



## background

background是一系列背景相关属性的**简写属性**

```css
[ <bg-layer> , ]* <final-bg-layer>where 
<bg-layer> = <bg-image> || <bg-position> [ / <bg-size> ]? || <repeat-style> || <attachment> || <box> || <box>
<final-bg-layer> = <'background-color'> || <bg-image> || <bg-position> [ / <bg-size> ]? || <repeat-style> || <attachment> || <box> || <box>
```



## background-image和img对比



|                        |   img    | **background-image** |
| ---------------------- | :------: | :------------------: |
| 性质                   | HTML元素 |       CSS样式        |
| 图片是否占用空间       |    √     |          ×           |
| 浏览器右键直接查看地址 |    √     |          ×           |
| 支持CSS Sprite         |    ×     |          √           |
| 更有可能被搜索引擎收录 |    √     |          ×           |



**总结**

- img，作为网页内容的重要组成部分，比如广告图片、LOGO图片、文章配图、产品图片
- background-image，可有可无。有，能让网页更加美观。无，也不影响用户获取完整的网页内容信息



# CSS盒子模型

HTML每一个元素看出一个个的盒子:

<img src="/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/box0.png" alt="box0" style="zoom:67%;" />

-  **内容(content)**
   - 元素的内容width/height
-  **内边距(padding)**
   - 元素和内容之间的间距
-  **边框(border)**
   - 元素自己的边框
-  **外边距(margin)**
   - 元素和其他元素之间的间距

因为盒子有四边, 所以margin/padding/border都包括**top/right/bottom/left**四个边:

<img src="/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/box.png" alt="box" style="zoom: 50%;" />

**在浏览器中**

<img src="/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/box1.png" alt="box1" style="zoom: 50%;" />



## 内容 – 宽度和高度

 设置内容是通过宽度和高度设置的:

- 宽度设置: width
- 高度设置: height

默认值为auto

注意: 对于**行内级非替换元素(inline-level)来说, 设置宽高是无效的!**

另外我们还可以设置如下属性:

- **`min-width`**:最小宽度，无论内容多少，宽度都大于或等于min-width
- **`max-width`:**最大宽度，无论内容多少，宽度都小于或等于max-width 

移动端适配时, 可以设置**最大宽度和最小宽度;**

```css
    .home {
      height: 2000px;
      background-color: #f00;

      /* 最大的宽度: 750px */
      max-width: 750px;

      /* 最小的宽度: 500px */
      min-width: 600px;

      /* 块级元素居中 */
      margin: 0 auto;
    }
```

下面两个属性不常用:

min-height:最小高度，无论内容多少，高度都大于或等于min-height

max-height:最大高度，无论内容多少，高度都小于或等于max-height



## 内边距 - padding

 padding属性用于设置盒子的内边距, 通常用于**设置边框和内容之间的间距;**

- **在<u>父子元素</u>中,父元素设置padding,**
- **如果不想父元素被子元素撑大,可以设置` box-sizing: border-box;`**

padding包括四个方向, 所以有如下的取值: 

- `padding-top`:上内边距
- `padding-right`:右内边距
- `padding-bottom`:下内边距
- `padding-left`:左内边距

padding单独编写是一个**缩写属性**:

- padding-top、padding-right、padding-bottom、padding-left的简写属性
- padding缩写属性是**从零点钟方向开始, 沿着<u>顺时针转动</u>的, 也就是 上右下左;**

不一定要写全

![](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/padding.png)

```css
    .box {
      /* 设置一个红色的实体边框 */
      border: 1px solid red;
      display: inline-block;

      /* line-height */
      /* line-height: 36px; */

      /* 内边距: padding */
      /* padding-top: 10px;
      padding-right: 20px;
      padding-bottom: 30px;
      padding-left: 40px; */

      /* 等价于: 缩写属性 */
      padding: 10px 20px 30px 40px;

      /* 其他值的情况 */
      /* 3个值 */
      /* 省略left -> 使用right */
      padding: 10px 20px 30px;
      /* 2个值 */
      /* 省略: left -> 使用right */
      /* 省略: bottom -> 使用top */
      padding: 10px 20px;
      /* 1个值 */
      /* 上下左右都使用同一个值 */
      padding: 10px;
    }
```



## 边框 - border

**border用于设置盒子的边框**

边框相对于content/padding/margin来说特殊一些:

- 边框具备宽度width;
- 边框具备样式style;
- 边框具备颜色color;

都有四个方向

设置边框的方式

- 边框宽度
  - border-top-width、border-right-width、border-bottom-width、border-left-width
  - **border-width**是上面4个属性的简写属性
- 边框颜色
  - border-top-color、border-right-color、border-bottom-color、border-left-color
  - **border-color**是上面4个属性的简写属性
- 边框样式
  - border-top-style、border-right-style、border-bottom-style、border-left-style
  - **border-style**是上面4个属性的简写属性

边框样式

- groove:凹槽, 沟槽, 边框看上去好象是雕刻在画布之内
- ridge:山脊, 和grove相反，边框看上去好象是从画布中凸出来

![border](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/border.png)

```js
    .box {
      display: inline-block;

      width: 300px;
      height: 300px;

      /* width */
      /* border-top-width: 10px;
      border-right-width: 20px;
      border-bottom-width: 30px;
      border-left-width: 40px; */
      /* border-width: 10px 20px 30px 40px; */

      /* style */
      /* border-top-style: solid;
      border-right-style: dashed;
      border-bottom-style: groove;
      border-left-style: ridge; */
      /* border-style: solid dashed groove ridge; */

      /* color */
      /* border-top-color: red;
      border-right-color: blue;
      border-bottom-color: green;
      border-left-color: orange; */
      /* border-color: red blue green orange; */

      /* 总缩写属性 */
      border: 10px solid red;
    }
```





## 圆角 – border-radius

**用于设置盒子的圆角**

 border-radius常见的值:

- **数值**: 通常用来设置小的圆角, 比如6px;
- 百分比: 通常用来设置一定的弧度或者圆形;

border-radius事实上是一个**缩写属性**:

- 将这四个属性 border-top-left-radius、border-top-right-radius、border-bottom-right-radius，和 border-bottom- left-radius 简写为一个属性。

如果一个元素是正方形, **<u>设置border-radius大于或等于50%时，就会变成一个圆</u>.**

![border-radius](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/border-radius.png)



## 外边距 - margin

**margin属性用于设置盒子的外边距, 通常用于元素和元素之间的间距;**  

margin包括四个方向, 所以有如下的取值: 

- `margin-top`:上内边距
- `margin-right`:右内边距
- `margin-bottom`:下内边距
- `margin-left`:左内边距

***行内级元素设置上下无效***

margin单独编写是一个**缩写属性**:

- margin-top、margin-right、margin-bottom、margin-left的简写属性
- margin缩写属性是从零点钟方向开始, 沿着顺时针转动的, 也就是**上右下左;**

margin也并非必须是四个值, 也可以有其他值;

![margin](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/margin.png)

- `margin:0,auto;`水平居中

### margin塌陷

####  上下margin的传递

**margin-top传递**

如果**块级元素的顶部线和父元素的顶部线重叠**，那么**这个块级元素的margin-top值会传递给父元素** 



**margin-bottom传递** 比较少见

如果**块级元素的底部线和父元素的底部线重叠，并且父元素的高度是auto(默认)，那么这个块级元素的margin-bottom值会传递给父元素**

**如何防止出现传递问题?**

- **给父元素设置padding-top\padding-bottom而不是让子元素设置margin**
- **给父元素设置border** `border: 1px solid transparent */` 边框设置为0,还是会传递
- **触发外层BFC**: 设置overflow为auto
  - BFC:block formatting context 为块设置独立空间不受影响

**建议**

- `margin`一般是用来设置**兄弟元素之间的间距**
- `padding`一般是用来设置**父子元素之间的间距**
  - 父元素设置padding  `box-sizing: border-box;`



#### 上下margin的折叠

**垂直方向**上相邻的2个margin(**margin-top、margin-bottom**)有可能会**合并为1个margin**，这种现象叫做collapse(折叠)

**水平方向**上的margin(margin-left、margin-right)永**远不会collapse**  margin会相加

**折叠后最终值的计算规则**

- 两个值进行比较，**取较大的值**

**如何防止margin collapse?**

- **只设置其中一个元素的margin**

**上下margin折叠的情况**

- 两个**兄弟块级元素之间上下margin的折叠**
- **父子块级元素之间margin的折叠**

<img src="/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/collapse1.png" alt="collapse1" style="zoom:67%;" />

![collapse2](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/collapse2.png)





## ▶元素的水平居中方案

 在一些需求中，需要<u>元素在父元素中水平居中显示(</u>父元素一般都是块级元素、inline-block)

- **行内级元素(包括inline-block元素)**
  - 水平居中:在**父元素中设置text-align: center** (只能文字)

- **块级元素**(block box )
  - 水平居中:**margin: 0 auto**
  - `display: inline-block;` 然后`text-align: center ` (只能文字)

**block盒子宽度=width + padding + · + margin(自动填充到最右)**

```css
margin-left: auto;
margin-right: auto;
margin-top: 0;
margin-bottom: 0;
/*等价于*/
margin: 0 auto
```



## **外轮廓** - outline

**outline表示元素的外轮廓**

- **不占用空间**

- **默认显示在border的外面**

**outline相关属性有**

- `outline-width:` 外轮廓的宽度

- `outline-style`:取值跟border的样式一样，比如solid、dotted等

- `outline-color`: 外轮廓的颜色
- `outline`  outline-width、outline-style、outline-color的简写属性，跟border用法类似

应用实例

- 去除a元素、input元素的focus轮廓效果
  - `outline:none;`

![outline](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/outline.png)



## 盒子阴影 – box-shadow

**box-shadow属性可以设置一个或者多个阴影**

**每个阴影用<shadow>表示**

多个阴影之间用**逗号,**隔开，从前到后叠加

**<shadow>的常见格式如下**

- none

- 第1个<length>:**offset-x, 水平方向的偏移，正数往右偏移**
- 第2个<length>:**offset-y, 垂直方向的偏移，正数往下偏移**
- 第3个<length>:**blur-radius, 模糊半径**
- 第4个<length>:**spread-radius, 延伸半径**
- <color>:**阴影的颜色，如果没有设置，就跟随color属性的颜色**
- **inset:外框阴影变成内框阴影**

```css
box-shadow: 5px 5px 10px orange, 10px 10px 10px green;
```

### 在线配置

https://html-css-js.com/css/generator/box-shadow/



## 文字阴影 - text-shadow

**text-shadow用法类似于box-shadow，用于给文字添加阴影效果**

 常见格式相当于box-shadow, 它没有spread-radius的值;



## 行内非替换元素的注意事项

**以下属性对行内级非替换元素<u>不起作用</u>**

(inline-level不能设置宽高)

- width、height、**margin-top、margin-bottom**

**以下属性对行内级非替换元素的效果比较<u>特殊</u>**

-  内边距: padding
   - 特殊:  左右有空间,上下会被撑起来,但是不占据空间
-  边框:  border
   - 特殊: **左右有空间**,**上下会被撑起来,** 但是**不占据空间** 
   - ![inline-border](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/inline-border.png)
-  外边距: margin
   - **上下的margin是不生效的**

## CSS属性 - box-sizing 

**box-sizing用来设置盒子模型中宽高的行为**

- content-box
  - padding、border**都布置在width、height外边**

- **border-box** 边框盒子
  - padding、border**都布置在width、height  里边**

![ie盒子模型](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/ie盒子模型.png)



# CSS元素定位

## 标准流布局

默认情况下，元素都是按照normal flow(标准流、常规流、正常流、文档流【document flow】)进行排布

- **从左到右、从上到下**按顺序摆放好
- 默认情况下，互相之间**不存在层叠现象**

![normal-flow](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/normal-flow.png)

**在标准流中，可以使用margin、padding对元素进行定位**

- ​	其中margin可以设置负数

**比较明显的缺点是** 

- 设置一个元素的margin或者padding，通常会**影响到标准流中其他元素的定位效果**
- 不便于实现**元素层叠**的效果

可以通过CSS设置**position**属性来进行**单独的对某个元素进行定位**,脱离跳出标准流



## 元素的定位

 定位允许您从正常的文档流布局中取出元素，并使它们具有不同的行为:

- 例如**放在另一个元素的上面;**
- 或者**始终保持在浏览器视窗内的同一位置;**



### position属性

```css
static | relative | fixed | absolute | sticky
```

默认值: static: 静态定位

- 元素**按照normal flow布局**
- left 、right、top、bottom**没有任何作用**



使用下面的值, 可以让元素变成**定位元素(positioned element) **:

- **relative**:相对定位
- **absolute**:绝对定位
- **fixed**:固定定位
- **sticky**:粘性定位

**`left 、right、top、bottom`生效**



### **定位元素(positioned element)**

- position值**不为static的元素**
- 也就是position值为**relative、absolute、fixed**的元素



### 定位元素的特点

- **可以随意设置宽高**
- **宽高默认由内容决定**
- **不再受标准流的约束**   脱标后都可以设置宽高
  - **不再严格按照从上到下、从左到右排布**
  - **不再严格区分块级、行内级，块级、行内级的很多特性都会消失**
- **不再给父元素汇报宽高数据**
  - ![定位元素的特点1](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/定位元素的特点1.png)
- **脱标元素内部默认还是按照标准流布局**



## **相对定位** - relative

元素按照**normal flow布局 ** **不脱离标准流**

**可以通过left、right、top、bottom进行定位**

- 定位参照对象**元素自己原来的位置**

**相对定位的应用场景**

- 在不影响其他元素位置的前提下，对**当前元素位置进行微调**

left、right、top、bottom用来设置元素的具体位置，对元素的作用如下图所示

![relative](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/relative.png)



**案例**-——相对定位实现图片居中

```css
  <style>
  /* 相对定位实现图片居中 */
    body {
      margin: 0;
      padding: 0;
    }
    .box{
      height: 480px;
      background-color: #f00;
      overflow: hidden;
    }

    .box img{
      position: relative;
      /* 1.左移图片的一半 */
      /* left: -960px; */
      /* 2.translate中的百分比是相对于自己 */
      transform: translate(-50%);
      /* <translate()> = translate( <length-percentage> , <length-percentage>? ) */
      /* 右移div的一半 */
      margin-left: 50%; 
    }
  </style>
```

```html
    <div class="box">
      <img src="../images/mhxy.jpg"> <!-- 1920*480 -->
    </div>
```





## 固定定位 - fixed

元素脱离normal flow(脱离标准流、脱标)

- 可以**通过left、right、top、bottom进行定位** 
- **定位参照对象是视口(viewport)**
- **当画布滚动时，固定不动**

```css
    .text {
      position: fixed;
      right: 30px;
      bottom: 30px;
    }
```



## 绝对定位 - absolute

元素脱离normal flow(脱离标准流、脱标)

**可以通过left、right、top、bottom进行定位**

- **定位参照对象是<u>最邻近</u>的<u>定位祖先元素</u>**
- 如果找不到这样的祖先元素，参照对象是视口

### 子绝父相

 **在绝大数情况下，子元素的绝对定位都是相对于父元素进行定位** 不一定 只要相当于定位元素就行

如果希望**子元素相对于父元素进行定位，又不希望父元素脱标**，常用解决方案是: 

- 父元素设置position: relative(让父元素成为定位元素，而且父元素不脱离标准流)
- 子元素设置position: absolute

**简称为“子绝父相”**



### 绝对定位元素元素的特点

- **绝对定位元素(absolutely positioned element)**

  - position值为**absolute**或者**fixed**的元素

- **对于绝对定位元素来说**

  - **定位参照对象的宽度 = left + right + margin-left + margin-right + 绝对定位元素的实际占用宽度**
  - **定位参照对象的高度 = top + bottom + margin-top + margin-bottom + 绝对定位元素的实际占用高度**

  公式推导⬇️

- 如果希望绝对定位元素的**宽高**和定位参照对象**一样**(独占一行)，可以给绝对定位元素设置以下属性 

  - **left: 0、right: 0、top: 0、bottom: 0、margin:0**

- 如果希望绝对定位元素在定位参照对象中**居中显示**，可以给绝对定位元素设置以下属性 

  - **left: 0、right: 0、top: 0、bottom: 0、margin: auto**
  - 另外，还得**设置具体的宽高值**(宽高小于定位参照对象的宽高)

  

**width: auto;**

- 行内非替换元素 -> width: 包裹内容
- 块级元素 ->width: 包含块的宽度
- 绝对定位元素 -> width: 包裹内容



## 粘性定位 - sticky

可以看做是**相对定位**和**固定(绝对)定位**的结合体;

- 它允许被定位的元素**表现得像相对定位一样**，直到它滚动到某个阈值点;

- **当达到这个阈值点时, 就会变成固定(绝对)定位;**

```css
position: sticky; /* 至少设置一个方向 */ 
top: 0px;/* 距离0px的时候停留 */ 
```

- sticky是相对于最近的**滚动祖先**包含滚动视口的

![sticky](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/sticky.png)



## position值的对比

![position值对比](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/position值对比.png)



## CSS属性 - z-index

z-index属性用来设置**定位元素**的层叠顺序(仅对**定位元素**有效)

- 取值可以是正整数、负整数、0(默认)

<img src="/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/z-index.png" alt="z-index" style="zoom:67%;" />



**比较原则**

- 如果是**兄弟关系**

  - <u>**z-index越大，层叠在越上面**</u>

  - z-index相等，写在后面的那个元素层叠在上面 

- 如果**不是兄弟关系**

  - 各自**从元素自己以及祖先元素中**，**找出最邻近的2个定位元素进行比较** (不是兄弟关系不能比较)

  - 而且这2个定位元素**必须有设置z-index的具体数值**





# 浮动-float

float 属性可以指定一个元素**应沿其容器的左侧或右侧放置**，**允许文本和内联元素环绕它**。

float 属性最初只用于**在一段文本内浮动图像,** **实现文字环绕的效果**

但是早期的CSS标准中并没有提供好的左右布局方案, 因此在一段时间里面它成为网页多列布局的最常用工具;

- 绝对定位、浮动都会让元素脱离标准流，以达到灵活布局的效果

- 可以通过float属性让元素产生浮动效果，float的常用取值

- none:不浮动，默认值
- **left:向左浮动**
- **right:向右浮动**



## 浮动规则

- 元素一旦浮动后, **脱离标准流**

  - 朝着向左或向右方向移动，**直到自己的边界紧贴着包含块**(一般是父元素)或者其他浮动元素的边界为止

  - **定位元素会层叠在浮动元素上面**

- **如果元素是向左(右)浮动，浮动元素的左(右)边界不能超出包含块的左(右)边界**

- **浮动元素之间不能层叠**
  - 如果**一个元素浮动，另一个浮动元素已经在那个位置了，<u>后浮动的元素将紧贴着前一个浮动元素</u>**(左浮找左浮，右浮找右浮
  - 如果**水平方向剩余的空间不够显示浮动元素，浮动元素将向下移动**，直到有充足的空间为止

![float](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/float.png)

-  **浮动元素不能与行内级内容层叠，行内级内容将会被浮动元素<u>推出</u>**   只能左右浮动,不能上下
   - 比如行内级元素、inline-block元素、块级元素的文字内容
-  **行内级元素**(inline)、**inline-block**元素浮动后，**其顶部将与所在行的顶部对齐**

 **浮动常用的场景**

- 决行内级元素、inline-block元素的水平间隙问题

- 可以让列表变成水平

  将多个行内级元素中间的空格(间隙)去除的方法

      1. 删除换行符(不推荐)
      2. 将父级元素的font-size设置为0, 但是需要子元素设置回来
      3. 通过子元素(span)统一向一个方向浮动即可
      4. flex布局



## 浮动的问题 – 高度塌陷

由于浮动元素脱离了标准流，变成了**脱标元素，所以不再向父元素汇报高度**

- **父元素计算总高度时，就不会计算浮动子元素的高度**，导致了高度坍塌的问题

解决父元素高度坍塌问题的过程，一般叫做**清浮动(清理浮动、清除浮动)**

**清浮动的目的是** 

- **让父元素计算总高度的时候，把浮动子元素的高度算进去**

如何清除浮动呢——**使用clear属性**



## CSS属性 - clear

clear属性是做什么的呢?

- clear 属性**可以指定一个元素是否必须移动**(清除浮动后)**到在它之前的浮动元素下面**

**clear的常用取值**

- `left`:要求元素的顶部低于之前生成的所有左浮动元素的底部
- `right`:要求元素的顶部低于之前生成的所有**右浮动**元素的底部
- **`both`:**要求元素的顶部低于之前生成的**所有浮动元素的底部**
- `none`:默认值，无特殊要求

可以利用这个特性来清除浮动



## 清除浮动的方法

事实上我们有很多方法可以清除浮动

方法一: **给父元素设置固定高度——扩展性不好(不推荐)**

方法二: **在父元素最后增加一个空的块级子元素，并且让它设置clear: both**

- 会增加很多无意义的空标签，维护麻烦
- 违反了结构与样式分离的原则(不推荐)

**▶方法三: 给父元素添加一个伪元素 (推荐)**

- **给父元素增加::after伪元素**
- 纯CSS样式解决，结构与样式分离(推荐)

```js
.clear_fix::after {
  content: "";
  clear: both;
  display: block;

  /* 浏览器兼容 */
  visibility: hidden;
  height: 0;
}
.clear_fix {
  /* IE6/7 */
  *zoom: 1;
}
```

# 布局总结

| **定位方案**                   | **应用场景** |
| :----------------------------- | :----------: |
| normal flow(标准流)            |   垂直布局   |
| absolute positioning(绝对定位) |   层叠布局   |
| float(浮动)                    |   水平布局   |



# CSS Flex布局



弹性盒子是一种**用于按行或按列布局元素的一维布局方法 ;**

**元素可以膨胀以填充额外的空间, 收缩以适应更小的空间;**

通常我们使用**Flexbox**来进行布局的方案称之为flex布局(flex layout); flex 布局(Flexible 布局，弹性布局);

**flex布局是目前web开发中使用最多的布局方案:**

- 目前特别在移动端可以说已经完全普及;
- 在PC端也几乎已经完全普及和使用, 只有非常少数的网站依然在用浮动来布局;

**原来的布局存在哪些痛点呢**

长久以来，CSS 布局中唯一可靠且跨浏览器兼容的布局工具只有 floats 和 positioning。 

但是这两种方法本身存在很大的**局限性**, 并且他们用于布局实在是无奈之举;

- 比如在父内容里面垂直居中一个块内容。
- 比如使容器的所有子项等分可用宽度/高度，而不管有多少宽度/高度可用。
- 比如使多列布局中的所有列采用相同的高度，即使它们包含的内容量不同。

*https://flexboxfroggy.com/*

## flex布局的重要概念

**两个重要的概念:**

- 开启了 flex 布局的元素叫 **flex container**
- flex container 里面的**直接子元素**叫做 **flex item**

**当flex container中的子元素变成了flex item时, 具备一下特点:**

- flex item的布局将**受flex container属性的设置来进行控制和布局;**
- flex <u>item</u>**不再严格区分块级元素和行内级元素;**
- flex item**默认情况下是包裹内容**的, 但是**可以设置宽度和高度;**

**设置 display 属性为 flex 或者 inline-flex 可以成为 flex container**

- `flex`: <u>flex container</u> **以 block-level 形式存在**
- `inline-flex`: <u>flex container</u> **以 inline-level 形式存在**

![flex1](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/flex1.png)

## flex模型

![flex-model](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/flex-model.png)

- main axis 主轴
- cross axis 交叉轴



## flex属性⬇️

 **flex container**

- flex-flow 简写属性
- flex-direction 主轴方向
- flex-wrap 换行
- justify-content 主轴item的分布方式
- align-items items在交叉轴上的的对齐方式
- align-content  和justify-content类似 多行items 在 交叉轴 上的对齐方式

 **flex items** 

- flex-grow
- flex-basis
- flex-shrink
- order
- align-self
- flex



### flex-direction

flex items **默认都是沿着 main axis(主轴)从 main start 开始往 main end 方向排布**

**flex-direction 决定了 main axis 的方向，有 4 个取值**

- `row`(默认值)(行)、`row-reverse`(行-反转)、`column`(列)、`column-reverse`(列-反转)

![flex-direction](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/flex-direction.png)



### flex-wrap

**flex-wrap 决定了 flex container 是单行还是多行**

-  `nowrap`(默认):单行
-  `wrap`:多行
-  `wrap-reverse`:多行(对比 wrap，cross start 与 cross end 相反)

![flex-wrap](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/flex-wrap.png)



### flex-flow 简写属性

flex-flow 属性是 **flex-direction** 和 **flex-wrap** 的简写。任何顺序, 并且都可以省略;



### justify-content 常用

 **justify-content** **决定了** **flex items** **在** **main axis** **上的对齐方式**

**`flex-start`**(默认值):与 main start 对齐

**`flex-end`**:与 main end 对齐

**`center`**:<u>居中对齐</u>

**`space-between`:**

- flex items <u>之间的距离相等</u>
- <u>与 main start、main end两端对齐</u>

**`space-around`**:

- flex items <u>之间的距离相等</u>
- flex items <u>与 main start、main end 之间的距离是 flex items 之间距离的一半</u>

**`space-evenly`**:

- flex items <u>之间的距离相等</u>
- flex items <u>与 main start、main end 之间的距离 等于 flex items 之间的距离</u>



```css
           /* 切换justify-content */
      /* flex-end: 让元素和main end对齐 */
      /* center: 居中对齐 */
      /* space-between: 两端各放一个元素, 其他多余的元素一定要空间等分 */
      /* space-evenly: 两端也有间距, 并且所有的空间进行等分 */
      /* space-around: 两端也有间距, 两端的间距是items之间的间距一半 */
```



![flex-justify-content](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/flex-justify-content.png)



### align-items 常用

**align-items 决定了 flex items 在 <u>cross axis</u> 上的对齐方式**

- **normal**:(默认值) 在弹性布局中，效果和stretch一样
- **stretch**:当 flex items **在 cross axis 方向的 size 为 auto 时(height=auto;)**，会 自动拉伸至填充 flex container <u>不能指定高度</u>
- **flex-start**:与 cross start 对齐
- **flex-end:**与 cross end 对齐 
- **center**:居中对齐
- **baseline**:<u>与基准线对齐</u>

![flex-align-item](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/flex-align-item.png)



### align-content

(container不设置高度,默认就是flex-start)

align-content **决定了多行 flex items 在 cross axis 上的对齐方式，用法与 justify-content 类似**

**stretch**(默认值):与 align-items 的 stretch 类似

**flex-start**:与 cross start 对齐

**flex-end**:与 cross end 对齐

**center**:居中对齐

**space-between**:

- flex items 之间的距离相等
- 与 cross start、cross end两端对齐

**space-around**:

- flex items 之间的距离相等
- flex items 与 cross start、cross end 之间的距离是 flex items 之间距离的一半

**space-evenly**:

- flex items 之间的距离相等
- flex items 与 cross start、cross end 之间的距离 等于 flex items 之间的距离

![flex-align-content](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/flex-align-content.png)



### flex-item属性 - order

**order决定了flex items的排布顺序**


可以设置任意整数(正整数、负整数、0)，**值越小就越排在前面**  默认值是 0

![flex-item_order](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/flex-item_order.png)



### flex-item属性 -  align-self

tems 可以通过 **align-self 覆盖 flex container 设置的 align-items** 

- auto(默认值):遵从 flex container 的 align-items 设置

- stretch、flex-start、flex-end、center、baseline，效果跟 align-items 一致


![flex-items](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/flex-items.png)



### flex-item属性 - flex-grow

**flex-grow 决定了 flex items 如何扩展(拉伸/成长)**

flexbox不剩空间,**把剩余的size按照各item的flex-grow的比例分给item**

可以设置任意非负数字(正小数、正整数、0)，默认值是 0

当 flex container **在 main axis 方向上有剩余 size 时，flex-grow 属性才会有效**

- 如果**所有 flex items 的 flex-grow f总和 sum 超过 1**，每个 flex item 扩展的 size 为 flex container 的剩余 **size *(flex-grow / sum)**

- flex items 扩展后的**最终 size** **不能超过 max-width\max-height** 


![flex-grow](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/flex-grow.png)



### flex-item属性 - flex-shrink

**flex-shrink 决定了 flex items 如何收缩(缩小) 可以设置任意非负数字(正小数、正整数、0)，默认值是 1** 

当 flex items **在 main axis 方向上超过了 flex container 的 size，flex-shrink 属性才会有效**

如果所有 flex items 的 **flex-shrink 总和超过 1**，**每个 flex item 收缩的 size**为flex items **超出 flex container 的 size *** **收缩比例 / 所有 flex items 的收缩比例之和**

flex items 收缩后的**最终 size 不能小于 min-width\min-height**



### flex-item属性 - flex-basis

flex-basis 用来设置 flex items **在 main axis 方向上的 base size** 基础尺寸

**auto(默认值)**、**具体的宽度数值**(100px)

**决定 flex items 最终 base size 的因素**，从优先级高到低

1. max-width\max-height\min-width\min-height
2. flex-basis
3. width\height
4. 内容本身的 size

### flex-item属性 - flex 简写属性

```css
none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
```

flex 是 **flex-grow || flex-shrink || flex-basis** 的简写,flex 属性可以指定1个，2个或3个值。

**单值语法: 值必须为以下其中之一:**

- 一个无单位数(<number>): 它会被当作<flex-grow>的值
- 一个有效的宽度(width)值: 它会被当作 <flex-basis>的值
- 关键字none，auto或initial.

**双值语法: 第一个值必须为一个无单位数，并且它会被当作 <flex-grow> 的值**,**第二个值必须为以下之一:**

-  一个无单位数:它会被当作 <flex-shrink> 的值
-  一个有效的宽度值: 它会被当作 <flex-basis> 的值

**三值语法:**

- 第一个值必须为一个无单位数，并且它会被当作 <flex-grow> 的值
- 第二个值必须为一个无单位数，并且它会被当作 <flex-shrink>的值
- 第三个值必须为一个有效的宽度值， 并且它会被当作 <flex-basis> 的值



## flex布局常见问题

![flex-problem](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/flex-problem.png)

```html
    <style>
    .container {
      width: 500px;
      background-color: orange;

      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
    }

    .item {
      width: 110px;
      height: 140px;
    }

    .container > i {
      width: 110px;
    }

  </style>
  <div class="container">
    <div class="item item1">1</div>
    <div class="item item2">2</div>
    <div class="item item3">3</div>
    <div class="item item1">1</div>
    <div class="item item2">2</div>
    <div class="item item3">3</div>
    <div class="item item1">1</div>
    <div class="item item2">2</div>
    <div class="item item3">3</div>
    <div class="item item3">3</div>
    <!-- 添加i的个数是列数减-2 -->
   <i></i><i></i>
```

- 为什么i不显示?
  - 因为没有高度,内容为空
- 要加几个才能保证不论最后一行有几个元素都可以正常布局?
  - 本来应该是列数-1,只要不满都用i填充
  - 但是justify-content: space-between; 就算只有一个元素,也会两端对齐,所以设置为列数-2
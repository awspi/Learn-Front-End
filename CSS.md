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

用于设置			

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

只对**行内级(inline-level)元素有效**‼️

行内级元素: 包括行内非替换元素**span/a** 行内替换元素**img/input/inline-block**

- 块级元素设置`display: inline-block;`

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

可以**影响小写字母**的显示形式

- **normal**:常规显示
- **small-caps**:将小写字母替换为缩小过的大写字母
  * 小写字母以大写显示, 但是高度保持小写的高度




### line-height(常用)

**用于设置文本的行高** 

撑起block的高度

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

## CSS选择器



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
  </style>
<body>
  
  <div class="box">我是div元素</div>
  <p class="box">我是p元素</p>

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
    - 常通过 **content 属性**来为一个**行内级元素**添加修饰性的内容。**不能将`content:""`省略**
    
      - **不是行内级不生效**,块级可以设置display:inline-block;
    
      

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
- **:nth-child(2n)** n代表任意正整数和0
  - 是父元素中的第偶数个子元素(第2、4、6、8......个) 
  - 跟:nth-child(**even**)同义
- **:nth-child(2n + 1)**
  - n代表任意正整数和0
  - 是父元素中的第奇数个子元素(第1、3、5、7......个) 
  - 跟:nth-child(**odd**)同义
- **nth-child(-n + 2)**代表前2个子元素



 **:nth-last-child( )**

:nth-last-child()的语法跟:nth-child()类似，不同点是:nth-last-child()**从最后一个子元素开始往前计数** 

- :nth-last-child(1)，代表倒数第一个子元素
- :nth-last-child(-n + 2)，代表最后2个子元素



**:nth-of-type()**用法跟**:nth-child()**类似

- 不同点是:nth-of-type()计数时**只计算同种类型**的元素

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

- `:first-child`，等同于:nth-child(1)
- `:last-child`，等同于:nth-last-child(1)
- `:first-of-type`，等同于:nth-of-type(1)
- `:last-of-type`，等同于:nth-last-of-type(1)
- `:only-child`，是父元素中唯一的子元素
- `:only-of-type`，是父元素中唯一的这种类型的子元素

下面的伪类偶尔会使用:

- `:root` 根元素，就是HTML元素 
- **`:empty` 代表里面完全空白的元素**



#### 否定伪类

:not()的格式是:not(x)

- x是一个简单选择器
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


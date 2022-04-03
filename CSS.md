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

* font-size(fz)
* color
* background-color(bgc)
* width
* height

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
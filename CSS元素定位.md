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

- **可以随意设置宽高** (符合行内块级元素,但不是!)
- **宽高默认由内容决定**
- **不再受标准流的约束**
  - **不再严格按照从上到下、从左到右排布**
  - **不再严格区分块级、行内级，块级、行内级的很多特性都会消失**
- **不再给父元素汇报宽高数据**
  - ![定位元素的特点1](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/定位元素的特点1.png)
- **脱标元素内部默认还是按照标准流布局**



## **相对定位** - relative

元素按照**normal flow布局 ** **不脱离标准流**

**可以通过left、right、top、bottom进行定位**

- 定位参照对象**元素自己原来的位置**

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



**相对定位的应用场景**

- 在不影响其他元素位置的前提下，对**当前元素位置进行微调**



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

z-index属性用来设置**定位元素**的层叠顺序(仅对定位元素有效)

- 取值可以是正整数、负整数、0(默认)

<img src="/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/z-index.png" alt="z-index" style="zoom:67%;" />



**比较原则**

- 如果是**兄弟关系**

  - **z-index越大，层叠在越上面**

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
- left:向左浮动
- right:向右浮动



## 浮动规则

- 元素一旦浮动后, 脱离标准流

  - 朝着向左或向右方向移动，**直到自己的边界紧贴着包含块**(一般是父元素)或者其他浮动元素的边界为止

  - **定位元素会层叠在浮动元素上面**

- **如果元素是向左(右)浮动，浮动元素的左(右)边界不能超出包含块的左(右)边界**

- **浮动元素之间不能层叠**
  - 如果**一个元素浮动，另一个浮动元素已经在那个位置了，后浮动的元素将紧贴着前一个浮动元素**(左浮找左浮，右浮找右浮
  - 如果**水平方向剩余的空间不够显示浮动元素，浮动元素将向下移动**，直到有充足的空间为止

![float](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/float.png)

-  **浮动元素不能与行内级内容层叠，行内级内容将会被浮动元素<u>推出</u>**   只能左右浮动,不能上下
  - 比如行内级元素、inline-block元素、块级元素的文字内容
- **行内级元素**(inline)、**inline-block**元素浮动后，**其顶部将与所在行的顶部对齐**

 **浮动常用的场景**

- 决行内级元素、inline-block元素的水平间隙问题
- 可以让列表变成水平

    将多个行内级元素中间的空格(间隙)去除的方法
      1. 删除换行符(不推荐)
      2. 将父级元素的font-size设置为0, 但是需要子元素设置回来
      3. 通过子元素(span)统一向一个方向浮动即可
      4. flex布局


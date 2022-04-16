# CSS盒子模型

HTML每一个元素看出一个个的盒子:

<img src="/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/box0.png" alt="box0" style="zoom:67%;" />

-  **内容(content)**
  - 元素的内容width/height
- **内边距(padding)**
  - 元素和内容之间的间距
- **边框(border)**
  - 元素自己的边框
- **外边距(margin)**
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
  -  **border-color**是上面4个属性的简写属性
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
-  margin缩写属性是从零点钟方向开始, 沿着顺时针转动的, 也就是**上右下左;**

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





## 元素的水平居中方案

 在一些需求中，需要<u>元素在父元素中水平居中显示(</u>父元素一般都是块级元素、inline-block)

- **行内级元素(包括inline-block元素)**
  - 水平居中:在**父元素中设置text-align: center** (只能文字)

- **块级元素**
  - 水平居中:**margin: 0 auto**
  - `display: inline-block;` 然后`text-align: center`

块级元素 block box 

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
- 边框:  border
  - 特殊: **左右有空间**,**上下会被撑起来,** 但是**不占据空间** 
  - ![inline-border](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/inline-border.png)
- 外边距: margin
  - **上下的margin是不生效的**

## CSS属性 - box-sizing 

**box-sizing用来设置盒子模型中宽高的行为**

- content-box
  - padding、border**都布置在width、height外边**

- **border-box** 边框盒子
  - padding、border**都布置在width、height  里边**

![ie盒子模型](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/ie盒子模型.png)

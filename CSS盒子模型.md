# CSS盒子模型



HTML每一个元素看出一个个的盒子:

<img src="/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/box0.png" alt="box0" style="zoom:67%;" />

-  内容(content)
  - 元素的内容width/height
- 内边距(padding)
  - 元素和内容之间的间距
- 边框(border)
  - 元素自己的边框
- 外边距(margin)
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

注意: 对于行内级非替换元素来说, 设置宽高是无效的!

另外我们还可以设置如下属性:

- `min-width`:最小宽度，无论内容多少，宽度都大于或等于min-width
- `max-width`:最大宽度，无论内容多少，宽度都小于或等于max-width 

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

padding包括四个方向, 所以有如下的取值: 

- `padding-top`:上内边距
- `padding-right`:右内边距
- `padding-bottom`:下内边距
- `padding-left`:左内边距

padding单独编写是一个**缩写属性**:

- padding-top、padding-right、padding-bottom、padding-left的简写属性
- padding缩写属性是**从零点钟方向开始, 沿着顺时针转动的, 也就是 上右下左;**

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
  - border-width是上面4个属性的简写属性
- 边框颜色
  - border-top-color、border-right-color、border-bottom-color、border-left-color
  -  border-color是上面4个属性的简写属性
- 边框样式
  - border-top-style、border-right-style、border-bottom-style、border-left-style
  - border-style是上面4个属性的简写属性

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

- 数值: 通常用来设置小的圆角, 比如6px;
- 百分比: 通常用来设置一定的弧度或者圆形;

border-radius事实上是一个**缩写属性**:

- 将这四个属性 border-top-left-radius、border-top-right-radius、border-bottom-right-radius，和 border-bottom- left-radius 简写为一个属性。

如果一个元素是正方形, **设置border-radius大于或等于50%时，就会变成一个圆.**

![border-radius](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/border-radius.png)

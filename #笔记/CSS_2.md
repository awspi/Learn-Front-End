# CSS属性 - transform

CSS transform属性允许对某一个元素进行某些**形变, 包括旋转，缩放，倾斜或平移**等。

- 并非所有的盒子都可以进行transform的转换(通常行内级元素不能进行形变)
  -  比如对span、a元素等;

**`<transform-function>+`**

- **+: 一个或者多个, 并且多个之间以空格分隔**



**常见的函数transform function有:** 

- **平移:translate(x, y)**
- **缩放:scale(x, y)**
- **旋转:rotate(deg)**
- **倾斜:skew(deg, deg)**

## 位移 - translate

平移:`translate(x, y)`

这个CSS 函数用于移动元素在平面上的位置。

**值类型:**

- **数字**:100px
- **百分比**:参照元素本身( refer to the size of bounding box )

![image-20220504173502710](/Users/wsp/Library/Application Support/typora-user-images/image-20220504173502710.png)

- **translate是translateX和translateY函数的简写。**
- **translate的百分比可以完成一个元素的水平和垂直居中:**
- **translate函数相对于flex布局的兼容性会好一点点**
  - 不过目前flex布局已经非常普及，直接使用flex布局即可;

## 元素的水平和垂直居中方案

### **水平居中**

1. **行内级元素:** 
   - 设置父元素的`text-align: center`
2. **块级元素:** 
   - 设置当前块级元素(宽度) `margin: 0 auto;` 
3. **绝对定位**
   - 元素有宽度情况下, `left0/right0/margin: 0 auto;`
4. **flex**
   - `justify-content: center`



### 垂直居中

1. **绝对定位**
   1. 元素有高度情况下, top0/bottom0/margin: auto 0;
   2. 弊端:
      - 必须使用定位(脱离标准流)
      - 必须给元素设置高度

2. **flex布局(直接使用flex)**
   - 弊端:当前flex局部中所有的元素都会被垂直居中
   - 相对来说, 兼容性差一点点(基本可以忽略)
3. **top/translate(推荐)**
   1. `position: relative;`不脱离标准流
   2. **`top: 50%;`让元素向下位移父元素的50%**
   3. **`transform: translate(0, -50%);`让元素向上位移自身的50%** 

!![image-20220504194130255](/Users/wsp/Library/Application Support/typora-user-images/image-20220504194130255.png)



## 缩放 - scale

 缩放:`scale(x, y)`

scale() CSS 函数可改变元素的大小。

**值个数**

- 一个值时，设置x轴上的缩放
- 二个值时，设置x轴和y轴上的缩放

![image-20220504195250148](/Users/wsp/Library/Application Support/typora-user-images/image-20220504195250148.png)

**值类型:**

- 数字:
  - 1:保持不变 
  - 2:放大一倍
  - 0.5:缩小一半
- 百分比:不常用

- **scale函数时scaleX和scaleY的缩写**
- scale3d 



## 旋转 - rotate

 旋转`:rotate()`

**值类型:**

- 常用单位deg:旋转的角度( degrees )
  - 正数为顺时针
  - 负数为逆时针
- 度(degrees)、 百分度(gradians)、弧度(radians)或圈数(turn);

- **rotate函数是rotateZ函数的简写写法。**
- rotate3d



## 倾斜 - skew

倾斜 `kew(x, y)`

函数定义了一个元素在二维平面上的倾斜转换。

**值个数**

- 一个值时，表示x轴上的倾斜
- 二个值时，表示x轴和y轴上的倾斜

**值类型:**

deg:倾斜的角度 

- 正数为顺时针
- 负数为逆时针



## transform-origin

形变的原点

比如在进行scale缩放或者rotate旋转 skew时，都会有一个原点。 

一个值:

设置x轴的原点 

两个值:

- 设置x轴和y轴的原点
- **必须是length，percentage，或 left, center, right, top, bottom关键字中的一个** 
- length:从左上角开始计算
- percentage:参考元素本身大小



# 过渡动画 - transition

- CSS transitions 提供了一种在**更改CSS属性时控制动画速度的方法。**
- 可以让**CSS属性变化成为一个持续一段时间的过程**，而不是立即生效的;
- 比如将一个元素从一个位置移动到另外一个位置，默认在修改完CSS属性后会立即生效;
  - 可以通过CSS transition，让这个过程加上一定的动画效果，包括一定的曲线速率变化;

通常将两个状态之间的过渡称为**隐式过渡(implicit transitions)**，因为开始与结束之间的状态**由浏览器决定。**



**并非所有的CSS属性都可以执行动画的**

- 在MDN可执行动画的CSS属性中查询
  - https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_animated_properties

- 阅读CSS属性的文档说明

*哪个元素需要动画就写在那个元素上,不写在伪类上*

***如果不需要复原动画,可以写在伪类上**,相当于属性消失*

```css
		.box {
      transition: all linear .2s;
    }

		.box:hover {
      left: 100px;
      transform: translate(100px);
    }

///////////////如果不需要复原动画
		.box {
    }

		.box:hover {
      transition: all linear .2s;//
      left: 100px;
      transform: translate(100px);
    }
```



 **transition CSS 属性是 transition-property，transition-duration，transition-timing-function 和 transition-delay 的一个简写属性。**

- transition:  属性  花费时间   速度曲线   延时时间;

  - ~~~css
    transition: width 2s ease 1s;
    ~~~

-  **transition-property:指定应用过渡属性的名称**

  - `all`:所有属性都执行动画;

  - `none`:所有属性都不执行动画;

  - `CSS属性名称`:要执行动画的CSS属性名称，比如width、left、transform等;

- **transition-duration:指定过渡动画所需的时间 单位可以是秒(s)或毫秒(ms)**
- **transition-timing-function:指定动画的变化曲线**
  - https://developer.mozilla.org/zh-CN/docs/Web/CSS/transition-timing-function
- **transition-delay:指定过渡动画执行之前的等待时间**

# Animation

之前我们学习了transition来进行过渡动画，但是过渡动画有如下的缺点:

1. `transition`**只能定义开始状态和结束状态**，不能定义中间状态，也就是说只有两个状态;
2. `transition`**不能重复执行**，除非一再触发动画;
3. `transition`**需要在特定状态下会触发才能执行**，比如某个属性被修改了;

如果我们希望可以有更多状态的变化，我们可以使用**CSS Animation。**

**CSS Animation的使用分成两个步骤:**

1. **使用keyframes定义动画序列(每一帧动画如何执行)**
2. **配置动画执行的名称、持续时间、动画曲线、延迟、执行次数、方向等等**



## @keyframes规则

**可以使用@keyframes来定义多个变化状态，并且使用animation-name来声明匹配:** 

关键帧使用**percentage**来指定动画发生的时间点;

- **0%表示动画的第一时刻，100%表示动画的最终时刻;**
- 因为这两个时间点十分重要，所以还有特殊的别名:**from和to;**
  - 也就是说可以使用from和to关键字: 

## animation属性

**animation** 属性是 animation-name，animation-duration, animation-timing-function，animation-delay，animation- iteration-count，animation-direction，animation-fill-mode 和 animation-play-state 属性的一个简写属性形式。

```css
 animation: moveAnim linear 1s normal infinite ;
```



- `animation-name`:指定执行哪一个关键帧动画
- `animation-duration`:指定动画的持续时间
- `animation-timing-function`:指定动画的变化曲线
- `animation-delay`:指定延迟执行的时间
- `animation-iteration-count`:指定动画执行的次数，执行infinite表示无限动画
- `animation-direction:`指定方向，常用值normal和reverse
- `animation-fill-mode`:执行动画最后保留哪一个值 none:回到没有执行动画的位置
  - `forwards`:动画最后一帧的位置
  - `backwards:`动画第一帧的位置
- `animation-play-state`:指定动画运行或者暂停(在JavaScript中使用，用于暂停动画)

![animation](/Users/wsp/Documents/Front-End-b/Front-End-b/移动Web/笔记/animation.png)

**常用**

1. 动画名字参照css类选择器命名
2. 动画时长和延迟时间别忘了带单位 s 
3. **infinate**   无限循环动画（重复次数）
4. **alternate**  为反向 就是<u>左右来回执行动画</u>（跑马灯）
5. **forwards**  动画结束<u>停留在最后一帧状态</u>， 不循环状态使用
6. **linear**   让动画匀速执行 默认是ease(慢->快->慢)



# CSS属性 - vertical-align

![image-20220504224911509](/Users/wsp/Library/Application Support/typora-user-images/image-20220504224911509.png)



**`vertical-align`会影响 行内块级元素 在一个 行盒 中垂直方向的位置**

思考:一个div没有设置高度的时候，会不会有高度? 

- 没有内容，没有高度
- 有内容，内容撑起来高度

但是内容撑起来高度的本质是什么呢?

- 内容有行高(line-height)，撑起来了div的高度

行高为什么可以撑起div的高度?

- 这是因为line box的存在，并且line-box有一个特性，包裹每行的inline level 
- 而其中的文字是有行高的，必须将整个行高包裹进去，才算包裹这个line-level

那么，进一步思考:

如果这个div中有图片，文字，inline-block，甚至他们设置了margin这些属性呢?

**line-boxes一定会想办法包裹住当前行中所有的内容。**

- <u>baseline对齐</u>

**baseline**

- **文本的baseline是字母x的下方**
- **Inline-block默认的baseline是margin-bottom的底部(没有，就是盒子的底部)**
- **Inline-block有文本时，baseline是最后一行文本的x的下方**

## vertical-align属性值

- `baseline`(默认值):基线对齐(你得先明白什么是基线)
- `top`:把行内级盒子的顶部跟line boxes顶部对齐
- `middle`:行内级盒子的中心点与父盒基线加上x-height一半的线对齐
- `bottom`:把行内级盒子的底部跟line box底部对齐
- `<percentage>`:把行内级盒子提升或者下降一段距离(距离相对于line-height计算\元素高度)， 0%意味着同baseline一 样
- `<length>`:把行内级盒子提升或者下降一段距离，0cm意味着同baseline一样

**解决图片下边缘的间隙方法:**

- vertical-align设置成top/middle/bottom
- 将图片设置为block元素
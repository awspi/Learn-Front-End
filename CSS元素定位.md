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
static | relative | absolute | sticky | fixed
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



### 定位元素的特点

- **可以随意设置宽高**
- **宽高默认由内容决定**
- **不再受标准流的约束**
  - **不再严格按照从上到下、从左到右排布**
  - **不再严格区分块级、行内级，块级、行内级的很多特性都会消失**
- **不再给父元素汇报宽高数据**
- **脱标元素内部默认还是按照标准流布局**



## **相对定位** - relative

元素按照normal flow布局

可以通过left、right、top、bottom进行定位

- 定位参照对象**元素自己原来的位置**

left、right、top、bottom用来设置元素的具体位置，对元素的作用如下图所示

![relative](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/relative.png)



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



## 粘性定位

## z-index
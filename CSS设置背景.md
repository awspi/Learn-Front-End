# CSS设置背景

## background-image

- background-image**用于设置元素的背景图片**
  - **会盖在**(不是覆盖)background-color的上面 

- 如果设置了**多张图片**
  - 设置的第一张图片将显示在最上面，其他图片按顺序层叠在下面

**如果设置了背景图片后，元素没有具体的宽高，背景图片是不会显示出来的**

```
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
- 水平方向还可以设值:left、center、right
- 垂直方向还可以设值:top、center、bottom
- 如果只设置了1个方向，另一个方向默认是center

![background-position](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/background-position.png)

```css
.box {
  height: 489px;
  background-color: #f00;

  background-image: url(../images/mhxy.jpg);
  background-position: center;
}
```

## background-attachment

 **background-attachment决定背景图像的位置是在视口内固定，或者随着包含它的区块滚动。**

用的不多

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



总结

- img，作为网页内容的重要组成部分，比如广告图片、LOGO图片、文章配图、产品图片
- background-image，可有可无。有，能让网页更加美观。无，也不影响用户获取完整的网页内容信息
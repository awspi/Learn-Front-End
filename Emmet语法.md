# Emmet

 VsCode内置了Emmet语法,在后缀为.html/.css中输入缩写后按Tab/Enter键即会自动生成相应代码

## >(子代)和+(兄弟)

```html
 <!-- div>h1+p>span+strong>i -->
  <div>
    <h1></h1>
    <p>
      <span></span>
      <strong>
        <i></i>
      </strong>
    </p>
  </div>
```



## *(多个)和^(上一级)

```html
  <!-- ul>li*10 -->
  <ul>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
  </ul>

  <!-- div>span+p+(h1>span+i)+p -->
  <!-- div>span+p+h1>span+i^p -->
  <div>
    <span></span>
    <p></p>
    <h1><span></span><i></i></h1>
  </div>
  <p></p>

```



## ()(分组)

```html
<!-- div>(header>ul>li*2>a)+footer>p --> 
<div>
    <header>
      <ul>
        <li><a href=""></a></li>
        <li><a href=""></a></li>
      </ul>
    </header>
    <footer>
      <p></p>
    </footer>
  </div>
```



##  (常用) 属性(id属性、class属性、普通属性) {}(内容)

```html
	<!-- div#header+div#main>.container>a[href] -->
  <div id="header"></div>
  <div id="main">
    <div class="container"><a href=""></a></div>
  </div>

  <!-- a[href="http://www.baidu.com"]{百度一下} -->
	<a href="http://www.baidu.com">百度一下</a>
```



## $(数字)

```html
<!-- ul>li.item$*5 -->
  <ul>
    <li class="item1"></li>
    <li class="item2"></li>
    <li class="item3"></li>
    <li class="item4"></li>
    <li class="item5"></li>
  </ul>
```



## 隐式标签

```html
<!-- .box -->
<div class="box"></div>

  <!-- ul>.item$*5 -->
  <ul>
    <li class="item1"></li>
    <li class="item2"></li>
    <li class="item3"></li>
    <li class="item4"></li>
    <li class="item5"></li>
  </ul>
```



## CSS Emmet

![css_emmet](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/css_emmet.png)
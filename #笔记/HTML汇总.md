# HTML汇总

# 完整的html结构

## 文档类型声明

- `<!DOCTYPE html> ` document type
  -  HTML文档声明，告诉浏览器当前页面是**HTML5**页面;
  -  让浏览器用**HTML5的标准**去解析识别内容;
  -  必须放在**HTML文档的最前面，不能省略**，省略了会出现兼容性问题;

## html元素

- lang属性
  - lang=“en”表示这个HTML文档的语言是英文;
  - lang=“zh-CN”表示这个HTML文档的语言是中文;

## head元素

- **HTML head** **元素** 规定文档相关的**配置信息(也称之为元数据)，**包括文档的标题，引用的文档样式和脚本等。
  - 元数据(meta data)是描述数据的数据

**常见的设置**

### title

网页的标题

`<title>head元素的学习</title>`

### meta

网页的编码

`<meta charset="UTF-8">`

- 可以用于设置网页的字符编码，让浏览器更精准地显示每一个文字，不设置或者设置错误会导致乱码; 
- 一般都使用utf-8编码

## body元素

 body元素里面的内容将是你**在浏览器窗口中看到的东西**，也就是**网页的具体内容和结构**。

> **文档**: https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element

### h元素和p元素

在一个页面中通常会有一些比较**重要的文字作为标题**，这个时候我们可以使用**h**元素。

**标题** **(Heading)** **元素**呈现了六个不同的级别的标题

- Heading是头部的意思，通常会用来做标题

- ```
  <h1> 级别最高，而 <h6> 级别最低。 (其实就是css样式不同)
  ```

  

```html
  <!-- h元素 h1~h6 -->
  <h1>我是h1标题</h1>
  <h2>我是h2标题</h2>
  <h3>我是h3标题</h3>
  <h4>我是h4标题</h4>
  <h5>我是h5标题</h5>
  <h6>我是h6标题</h6>
```

 如果我们想表示一个**段落**，这个时候可以使用**p**元素。

`<p>`元素表示文本的一个段落。

- p元素是paragraph单词的缩写，是段落、分段的意思;
- p元素多个段落之间会有一定的间距;

**案例**![QQ20220401-172806@2x](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/QQ20220401-172806@2x.png)

```html
  <h1>HTML</h1>
  <p>
    HTML的全称为超文本标记语言，是一种标记语言。它包括一系列标签．通过这些标签可以将网络上的文档格式统一，使分散的Internet资源连接为一个逻辑整体。HTML文本是由HTML命令组成的描述性文本，HTML命令可以说明文字，图形、动画、声音、表格、链接等。 [1]
  </p>
  <p>
    超文本是一种组织信息的方式，它通过超级链接方法将文本中的文字、图表与其他信息媒体相关联。这些相互关联的信息媒体可能在同一文本中，也可能是其他文件，或是地理位置相距遥远的某台计算机上的文件。这种组织信息方式将分布在不同位置的信息资源用随机方式进行连接，为人们查找，检索信息提供方便。 [1] 
  </p>

```





### img

使用img元素**显示图片**

-  <img> 元素将一份图像嵌入文档。

-  事实上img是一个可替换元素( replaced element );

#### 属性

img有两个常见的**属性**:

- **src属性**:source单词的缩写，表示源
  -  是必须的，它包含了你想嵌入的图片的文件路径.

- **alt属性**:不是强制性的,有两个作用:

  - 当图片加载不成功(错误的地址或者图片资源不存在)，那么会显示这段文本;

  - 屏幕阅读器会将这些描述读给需要使用阅读器的使用者听，让他们知道图像的含义;

某些其他属性目前已经**不再使用**,使用css代替

- 比如width、height、border

```html
  <img src="../images/gouwujie01.jpg" alt="123">
```



#### **图片路径**

- 网络图片:一个URL地址

- 本地图片:本地图片，后续会和html一起部署到服务;

本地图片的路径有两种方式:

- **相对路径**
  -  相当于当前文件的一个路径;
     - **.** 代表当前文件夹,可以省略 
     - **..**  代表上级文件夹(2个.)
     - **/** 路径分隔符
- 绝对路径

#### 图片格式

- ...很多格式
- **webp**



### a

a标签用于跳转到新链接

 <a> **元素**(或称**锚**(anchor)元素)

- 定义**超链接**，用于打开新的URL;

#### 属性

- **href**:Hypertext Reference

  - 指定要打开的URL地址;
  - 也可以是一个本地地址;

- **target**:该属性指定在何处显示链接的资源。

  - _self:默认值，在当前窗口打开URL
  - _blank:在一个新的窗口中打开URL; 
  - _parent:在父窗口中打开URL 
  - _top:在顶层窗口中打开URL
  - 其他不常用, **iframe**

  

```html
<!-- http://www.baidu.com -> 百度的服务器 -> index.html文件 -->
  <a href="http://www.baidu.com" target="_blank">百度一下</a>

  <!-- 链接到本地的网页(本地的资源地址) -->
  <a href="./09_img元素中的图片路径.html" target="_self">本地网站</a>

```

####  

#### 锚点链接

锚点链接可以实现:跳转到**网页中的具体位置**

锚点链接有两个重要**步骤**

- 在要跳到的元素上**定义一个id属性**;id="id01"
- 定义**a**元素，并且a元素的**href指向对应的id**;href=" #id"

```html
<a href="#theme01">跳转到主题一</a>
<a href="#theme02">跳转到主题二</a>
<a href="#theme03">跳转到主题三</a>

<h2 id="theme01">主题一</h2>
<h2 id="theme02">主题一</h2>
<h2 id="theme03">主题一</h2>
```

#### a元素和img结合使用



```html
  <a href="https://github.com/" target="_blank">
    <img src="/images/muxing.jpg" alt="">
  </a>
```



#### 其他的URL地址

- 文件
- 邮箱 206002328@qq.com

```html
<!-- 指向链接: zip压缩包 -->
<a href="https://github.com/awspi/WebServer-Blog/archive/refs/heads/main.zip">下载zip包</a>
<!-- 指向其他协议地址: mailto -->
<a href="mailto:206002328@qq.com">发邮件给</a>
```



### iframe元素

- 利用iframe元素可以实现:在一个HTML文档中嵌入其他HTML文档

- **frameborder**属性
- 用于规定是否显示边框 1:显示 0.不显示

```html
  <iframe src="http://www.taobao.com" width="800" height="600" frameborder="0"></iframe>
```



###  div/span

在HTML中有两个特殊的元素div元素、span元素:

- **div**元素:division 分开、分配的意思;
- **span**元素:跨域、涵盖的意思;



- 这两个元素有什么作用呢?无所用、无所不用。

- 产生的历史:

  - 网页的发展早期是没有css，这个时候我们必须通过语义化元素来告知浏览器一段文字如何显示; 
  - 后来出现了css，结构和样式需要分离，这个时候html只需要负责结构即可;

  

- 比如h1元素可以是一段**普通的文本+CSS修饰样式**;

- 这个时候就出现了div、span来编写HTML结构所有的结构，样式都交给css来处理;

- 所以，理论上来说:

  - 我们的页面可以没有div、span;
  - 我们的页面也可以全部都是div、span;



div元素和span元素都是“纯粹的” 容器，也可以把他们理解成“盒子”，它们都是用来包裹内容的

- **div**元素:多个div元素包裹的内容会在**不同的行**显示
  - 一般作为其他元素的父容器，把其他元素包住，代表一个整体 
  - 用于把网页分割为多个独立的部分
- **span**元素:多个span元素包裹的内容会在**同一行**显示
  - 默认情况下，跟普通文本几乎没差别
  - 用于区分特殊文本和普通文本，比如用来显示一些关键字



### 不常用元素

- **strong**元素:内容加粗、强调;
  - 通常加粗会使用css样式来完成;
  - 开发中很偶尔会使用一下;
- **i**元素:内容倾斜;
  - 通常斜体会使用css样式来完成;
  - 开发中偶尔会用它来做字体图标(因为看起来像是icon的缩写);
- **code**元素:用于显示代码
  - 偶尔会使用用来显示等宽字体;
- **br**元素:换行元素
  - 开发中已经不使用;

## HTML全局属性

有一些属性是**所有HTML都可以设置和拥有**的，这样的属性我们称之为 “全局属性(Global Attributes)”
全局属性有很多:https://developer.mozilla.org/zh-CN/docs/Web/HTML/Global_attributes 

常见的全局属性如下:

- **id**:定义唯一标识符(ID)，该标识符**在整个文档中必须是唯一**的。其目的是在链接(使用片段标识符)，脚本或样式(使用 CSS)时标识元素。
- **class**:一个**以空格分隔的元素的类名(classes )列表**，它允许 CSS 和 Javascript 通过**类选择器或者DOM方法来选择和访问特定的元素;**
- **style**:给元素添加内联样式;
- **title**:包含表示与其所属元素相关信息的文本。 这些信息通常可以作为提示呈现给用户，但不是必须的。



## 字符实体

* 为什么需要字符实体;
  * 如果使用小于号(<)，浏览器会将其后的文本解析为一个tag。 
  * 但是某些情况下，我们确实需要编写一个小于号(<);


HTML 实体是一段**以连字号(&)开头、以分号(;)结尾**的文本(字符串)

- 实体常常用于显示保留字符(这些字符会被解析为 HTML 代码)和不可见的字符(如“不换行空格”); 
- 也可以用实体来代替其他难以用标准键盘键入的字符;

* **三个常用:**

```
  &nbsp;
  &lt;
  &gt;
```

<img src="/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/QQ20220401-215944@2x.png" alt="QQ20220401-215944@2x" style="zoom: 50%;" />

## URL

URL 代表着是统一资源定位符(Uniform Resource Locator)

理论上说，每个有效的 URL 都指向一个唯一的资源; 可以是一个 HTML 页面，一个 CSS 文档，一幅图像，等等

* URL的格式:
  * 协议://主机:端口/路径/文件名?查询#片段id

![QQ20220401-223350@2x](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/QQ20220401-223350@2x.png)



* 和URI的区别:

  * URI:标志符
  * URL: 定位符(网络地址)

  

  URL的标准格式如下:

```
 [协议类型]://[服务器地址]:[端口号]/[文件路径][文件名]?[查询]#[片段ID]
```

- 和URI的区别:
  - URI = Uniform Resource Identifier **统一资源标志符**，用于标识 Web 技术使用的逻辑或物理资源。; 
  - URL = Uniform Resource Locator **统一资源定位符**，俗称网络地址，相当于网络中的门牌号;
- URI在某一个规则下能把一个资源独一无二的识别出来。
  - URL作为一个网络Web资源的地址，可以唯一将一个资源识别出来，所以URL是一个URI; 
  - **所以URL是URI的一个子集;**
  - 但是URI并不一定是URL

locators are also identifiers, so every URL is also a URI, but there are URIs which are not URLs.

# HTML高级元素

## 列表

### 列表的实现方式

- 方案一: 使用**div**元素来实现(比如汽车之家, 知乎上的很多列表)
- 方案二: 使用**列表**元素, 使用元素语义化的方式实现;

事实上现在很多的网站对于列表元素没有很强烈的偏好, 更加不拘一格, 按照自己的风格来布局:

原因是**列表元素默认的CSS样式**, 让它用起来不是非常方便;

比如**列表元素往往有很多的限制, ul/ol中只能存放li, li再存放其他元素, 默认样式等;**

虽然我们可以通过重置来解决, 但是我们更喜欢自由的div;

HTML提供了3组常用的用来展示列表的元素

- 有序列表:ol、li
- 无序列表:ul、li
- 定义列表:dl、dt、dd



### 有序列表 – ol – li

**ol(**ordered list)

- 有序列表，直接子元素只能是li

**li**(list item)

- 列表中的每一项

一般会把默认样式去除

```css
  <style>
    ol, li {
      padding: 0;
      margin: 0;
      list-style: none;
    }
  </style>
```



### 无序列表 – ul - li

**ul**(unordered list)

- 无序列表，直接子元素只能是**li**

**li**(list item)

- 列表中的每一项

实际上只是list-style-type`不同

```css
list-style-type: decimal;有序列表
list-style-type: disc;无序
list-style-type: none;无标识

```



### 定义列表 – dl – dt - dd

**dl**(definition list)

- **定义列表**，直接子元素只能是**dt、dd** 

**dt**(definition term)

- 列表中每一项的**项目名**

**dd**(definition description)

- 列表中每一项的**具体描述**，是对 dt 的描述、解释、补充

- **一个dt后面一般紧跟着1个或者多个dd**

对列表修改样式

```css
  <style>
    dl, dt, dd {
      padding: 0;
      margin: 0;
    }

    dt {
      font-size: 20px;
      font-weight: 700;
      margin: 10px 0;
    }

    dd {
      margin: 5px;
    }
  </style>
```



## 表格

某些内容的展示使用表格元素更为合适和方便

### 常见元素

- **table**
  - 表格
- **tr**(table row)
  - 表格中的行
- **td**(table data)
  - 行中的单元格
- 另外表格有很多相关的属性可以设置表格的样式, 但是已经**不推荐使用了**

**属性:**

`border-collapse` CSS 属性是用来决定**表格的边框是分开的还是合并的。** 

```css
table { border-collapse: collapse; }
```

**其他元素**

- `thead` 表格的表头
- `fftbody`表格的主体
- `tfoot`表格的页脚
- `caption`表格的标题
- `th` 表格的表头单元格

### 单元格合并

在某些特殊的情况下, 每个单元格占据的大小可能并不是固定的

- 一个单元格可能会跨多行或者多列来使用;

  单元格合并分成两 种情况: 

- **跨列合并: 使用colspan**

  - **在最左边的单元格**写上colspan属性, 并且省略掉合并的td;

- **跨行合并: 使用rowspan**

  - **在最上面的单元格**写上rowspan属性, 并且省略掉后面tr中的td;

![单元格跨列](/Users/wsp/Documents/Front-End/Code/Learn_HTML_CSS/img/单元格跨列.png)

## 表单

HTML表单元素是和用户交互的重要方式之一, 在很多网站都需要使用表单:

### 常见的表单元素

- `form` 表单, 一般情况下，**其他表单相关元素都是它的后代元素**
- `input` 单行文本输入框、单选框、复选框、按钮等元素 
- `textarea` 多行文本框 
- `select`、`option` 下拉选择框
- `button` 按钮
- `label` 表单元素的标题

#### form常见的属性

form通常作为表单元素的父元素: 

- form可以将整个表单**作为一个整体来进行操作;**
- 比如对整个表单进行重置;
- 比如对整个表单的数据进行提交;

form常见的属性如下:

-  action
   - 用于提交表单数据的请求URL
-  method
   - 请求方法(get和post)，默认是get
-  target
   - 在什么地方打开URL(参考a元素的target)

#### input元素

- type:input的类型
  - text:文本输入框(明文输入)
  - password:文本输入框(密文输入) 
  - radio:单选框
  - checkbox:复选框
  - button:按钮
  - reset:重置
  - submit:提交表单数据给服务器
  - file:文件上传
- readonly:只读
- disabled:禁用
- checked:默认被选中
  - 只有当type为radio或checkbox时可用
- autofocus:当页面加载时，自动聚焦
- name:名字
  - 在提交数据给服务器时，可用于区分数据类型 
- value:取值

*文档: https://developer.mozilla.org/zh- CN/docs/Web/HTML/Element/Input*

**布尔属性(boolean attributes)**

常见的布尔属性有disabled、checked、readonly、multiple、autofocus、selected

- 布尔属性**可以没有属性值，写上属性名就代表使用这个属性**
- 如果要给布尔属性设值，值就是属性名本身

```css
  <input type="text" readonly>
  <input type="text" readonly="readonly">
```

#### 表单按钮

**普通按钮(type="button")**:使用value属性设置按钮文字

**重置按钮(type="reset")**:重置它所属form的所有表单元素(包括input、textarea、select)

**提交按钮(type="submit"):**提交它所属form的表单数据给服务器(包括input、textarea、select)

```html
 			 <!-- 用input来实现按钮的效果 -->
      <input type="button" value="普通按钮">
      <button>普通按钮</button>
```

#### label和input的关系

**label元素一般跟input配合使用，用来表示input的标题**

- labe可以跟某个input绑定，**点击label就可以激活对应的input变成选中**

```html
  <div>
    <label for="username">
      用户: 
      <input id="username" type="text">
    </label>
    
  </div>
  <div>
    <label for="password">
      密码: 
      <input id="password" type="password">
    </label>
  </div>

```

#### 单选框

- 我们可以将type类型设置为**radio**变成单选框
- **name值相同的radio才具备单选功能**

```html
<!-- 在类型为radio的input中, 如果name一样, 那么两个radio就会互斥 -->
  <form action="/abc">
    <label for="male">
      <input id="male" type="radio" name="sex" value="male">男
    </label>
    <label for="female">
      <input id="female" type="radio" name="sex" value="female">女
    </label>

    <button type="submit">提交按钮</button>
  </form>
```



#### 多选框

- 我们可以将type类型设置为**checkbox**变成多选框:
  - **属于同一种类型的checkbox，name值要保持一致**

```html
<div>
  您的爱好:
  <label for="basketball">
    <input id="basketball" type="checkbox" name="hobby" checked value="basketball">篮球
  </label>
  <label for="football">
    <input id="football" type="checkbox" name="hobby" value="football">足球
  </label>
</div>
```



#### 多行输入框

**textarea**的常用属性

- `cols`:列数
- `rows`:行数
- `checked` 默认选中

缩放的**CSS设置**

-  禁止缩放:resize: none;
-  水平缩放:resize: horizontal;
-  垂直缩放:resize: vertical; 
-  水平垂直缩放:resize: both;

```css
textarea {
  resize: vertical;
}
```



#### 选项列表

 **option是select的子元素，一个option代表一个选项**

 select常用属性

- multiple:可以多选 
- size:显示多少项

option常用属性

- selected:默认被选中




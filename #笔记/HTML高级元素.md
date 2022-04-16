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

-  **一个dt后面一般紧跟着1个或者多个dd**

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
- target
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
- 水平垂直缩放:resize: both;

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

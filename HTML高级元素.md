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


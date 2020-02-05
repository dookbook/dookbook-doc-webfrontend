TOPICS: <table>
        <thead>
        <tbody>
        <tfoot>
        <th>
        <tr>
        <td>
        <caption>
        <colgroup>
        <col>
        <col> span attribute

# HTML 表格元素 `<table>`

**HTML 表格元素** (**`<table>`**) 元素表示**表格数据** — 即通过*行*和*列*的*单元格*组成的**二维表格**表示的信息。

**`<tr>`** 元素定义表格中的**行**。是由一个或多个 **`<td>`** （**数据单元格**）和 **`<th>`** （**标题单元格**）元素组成。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容* |
| **允许的内容** | 按照这个顺序：<br>1. 一个可选的 **`<caption>`** 元素<br>2. 零个或多个的 **`<colgroup>`** 元素<br>3. 一个可选的 **`<thead>`** 元素<br>4. 以下任选其一：4.1) 零个或多个 **<tbody>** 元素，4.2) 一个或多个 **`<tr>`** 元素，4.3) 一个可选的 **`<tfoot>`** 元素 |
| **标签省略** | 不允许，开始标签和结束标签都不能省略。 |
| **允许的父元素** | 任何支持 *流式内容* 的元素 |
| **允许的ARIA 角色** | Any |
| **DOM 接口** | **`HTMLTableElement`** |

## 属性

表格标签支持[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

### 不带标题单元格的简单表格

```html
<!-- 示例：简单表格 -->
<table>
  <tr>
    <td>数据单元格 第1行，第1列</td>
    <td>数据单元格 第1行，第2列</td>
  </tr>
  <tr>
    <td>数据单元格 第2行，第1列</td>
    <td>数据单元格 第2行，第2列</td>
  </tr>
</table>
```

## 带标题单元格的简单表格

```html
<!-- 示例：带标题单元格的简单表格 -->
<table>
  <tr>
    <th>标题单元格 第1列</th>
    <th>标题单元格 第2列</th>
  </tr>

  <tr>
    <td>数据单元格 第1行，第1列</td>
    <td>数据单元格 第1行，第2列</td>
  </tr>
  <tr>
    <td>数据单元格 第2行，第1列</td>
    <td>数据单元格 第2行，第2列</td>
  </tr>
</table>
```

**`<th>`** 定义表格内的**表头单元格**。这部分特征是由 **`scope`** and **`headers`** 属性准确定义的。

## 带标题的表格

```html
<!-- 示例：带标题的表格 -->
<table>
  <caption>表格标题</caption>

  <tr>
    <th>标题单元格 第1列</th>
    <th>标题单元格 第2列</th>
  </tr>
  <tr>
    <td>数据单元格 第1行，第1列</td>
    <td>数据单元格 第1行，第2列</td>
  </tr>
  <tr>
    <td>数据单元格 第2行，第1列</td>
    <td>数据单元格 第2行，第2列</td>
  </tr>
</table>
```

**HTML 表格标题元素** (**`<caption>`**) 展示一个表格的标题， 它常常作为 `<table>` 的**第一个**子元素出现，同时显示在表格内容的最前面。
但是，它的样式可以由 [[CSS]] **`caption-side`** 和 **`text-align`** 的属性自定义。

## 带 `<thead>`, `<tfoot>` 和 `<tbody>` 的表格

**`<thead>`** 元素封装了一组标题单元格（包含 *`<th>`* 的 *`<tr>`*）的表格行。

**`<tbody>`** 元素封装了一组数据单元格（包含 *`<td>`* 的 *`<tr>`*）的表格行。

**`<tfoot>`** 元素封装了一组表格中各列的汇总单元格（也是包含 *`<td>`* 的 *`<tr>`*）的表格行。

```html
<!-- 示例：带 `<thead>`, `<tfoot>` 和 `<tbody>` 的表格 -->
<table>
  <caption>表格标题</caption>

  <thead>
    <tr>
      <th>标题单元格 第1列</th>
      <th>标题单元格 第2列</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>数据单元格 第1行，第1列</td>
      <td>数据单元格 第1行，第2列</td>
    </tr>
    <tr>
      <td>数据单元格 第2行，第1列</td>
      <td>数据单元格 第2行，第2列</td>
    </tr>
  </tbody>

  <tfoot>
    <tr>
      <td>汇总单元格 第3行，第1列</td>
      <td>汇总单元格 第3行，第2列</td>
    </tr>
  </tfoot>
</table>
```

## 带列组的表格

**HTML 表格列组元素**（**`<colgroup>`**）用于对表格中的列进行组合，以便对其进行格式化。

如果想对 `<colgroup>` 中的某列定义不同的属性，请在 `<colgroup>` 元素内使用 *`<col>`* 元素。**`<col>`** 元素用于为表格中的一列或多列设置属性值。
`<col>` 的 **`span`** 属性定义了应该横跨的列数。

为 `<col>` 添加 **`class`** 属性，就可以使用 [[CSS]] 来定义对应列的样式了。

```html
<!-- 示例：带列组的表格 -->
<table>
  <caption>表格标题</caption>
  <colgroup>
    <col class="column1">  <!-- 标记第一列 -->
    <col class="columns2plus3" span="2">  <!-- 标记后两列 -->
  </colgroup>
  <tr>
    <th>Lime</th>
    <th>Lemon</th>
    <th>Orange</th>
  </tr>
  <tr>
    <td>Green</td>
    <td>Yellow</td>
    <td>Orange</td>
  </tr>
</table>
```

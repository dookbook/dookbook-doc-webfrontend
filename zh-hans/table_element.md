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
| **允许的内容** | 按照这个顺序：<br>1. 一个可选的 **`<caption>`** 元素<br>2. 零个或多个的 **`<colgroup>`** 元素<br>3. 一个可选的 **`<thead>`** 元素<br>4. 以下任选其一：4.1) 零个或多个 **`<tbody>`** 元素，4.2) 一个或多个 **`<tr>`** 元素，4.3) 一个可选的 **`<tfoot>`** 元素。 |
| **标签省略** | 不允许，开始标签和结束标签都不能省略。 |
| **允许的父元素** | 任何支持 *流式内容* 的元素。 |
| **允许的ARIA角色** | Any |
| **DOM 接口** | **`HTMLTableElement`** |

## 属性

表格标签支持[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

| 属性 | 描述 |
| :-- | :-- |
|border|规定表格单元是否拥有边框。|
|align|**HTML 4.01 已废弃。** 规定表格相对周围元素的对齐方式。|
|bgcolor|**HTML 4.01 已废弃。** 规定表格的背景颜色。|
|cellpadding|**HTML5不支持。** 规定单元边沿与其内容之间的空白。|
|cellspacing|**HTML5不支持。** 规定单元格之间的空白。|
|frame|**HTML5不支持。** 规定外侧边框的哪个部分是可见的。|
|rules|**HTML5 不支持。** 规定内侧边框的哪个部分是可见的。|
|summary|**HTML5 不支持。** 规定表格的摘要。|
|width|**HTML5 不支持。** 规定表格的宽度。|

## 示例

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

### 带标题单元格的简单表格

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

### 带标题的表格

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

### 空单元格

本例演示如何使用 "`&nbsp`;" 处理没有内容的单元格。

```html
<body>
<table border="1">
<tr>
  <td>一些文本</td>
  <td>一些文本</td>
</tr>
<tr>
  <td></td>
  <td>一些文本</td>
</tr>
</table>
<p>如果在上面的空单元格中没有边框，你可以插入一个空格 ： &amp;nbsp;</p>
</body>
```

### 带 `<thead>`, `<tfoot>` 和 `<tbody>` 的表格

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

### 带列组的表格

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

## 无障碍关注

### 标题

通过提供`<caption>`其值,清晰简洁地描述表格目的，它可以帮助人们决定是否需要阅读表格的其余内容或跳过表格的其余内容。

这可以帮助人们借助辅助技术（例如屏幕阅读器），当视力不好的条件下为人们认知问题的进行导航。

### 确定行和列的范围

`<header>`元素上的`<scope>`属性在简单上下文中是多余的，因为可以推断`<scope>`范围。但是，使用某些辅助技术可能无法得出正确的推论，因此指定标题范围可能会改善用户体验。在复杂表中，可以指定范围，以便提供标题相关的单元格必要信息。

```html
<table>
  <caption>Color names and values</caption>
  <tbody>
    <tr>
      <th scope="col">Name</th>
      <th scope="col">HEX</th>
      <th scope="col">HSLa</th>
      <th scope="col">RGBa</th>
    </tr>
    <tr>
      <th scope="row">Teal</th>
      <td><code>#51F6F6</code></td>
      <td><code>hsla(180, 90%, 64%, 1)</code></td>
      <td><code>rgba(81, 246, 246, 1)</code></td>
    </tr>
    <tr>
      <th scope="row">Goldenrod</th>
      <td><code>#F6BC57</code></td>
      <td><code>hsla(38, 90%, 65%, 1)</code></td>
      <td><code>rgba(246, 188, 87, 1)</code></td>
    </tr>
  </tbody>
</table>
```

提供`scope="col"`元素上的声明`<th>`将有助于描述该单元格在列的顶部。提供元素`scope="row"`上的声明`<td>`将有助于描述该单元格是行中的第一个单元格。

- [MDN Tables for visually impaired users](https://wiki.developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Advanced#Tables_for_visually_impaired_users)
- [Tables with two headers • Tables • W3C WAI Web Accessibility Tutorials](https://www.w3.org/WAI/tutorials/tables/multi-level/)
- [Tables with irregular headers • Tables • W3C WAI Web Accessibility Tutorials](https://www.w3.org/WAI/tutorials/tables/irregular/)
- [H63: Using the scope attribute to associate header cells and data cells in data tables | W3C
Techniques for WCAG 2.0](https://www.w3.org/TR/WCAG20-TECHS/H63.html)

### 复杂的表

诸如屏幕阅读器之类的辅助技术可能难以解析非常复杂的表，以致无法以严格的水平或垂直方式关联标题单元格。通常通过`colspan`和`rowspan`属性的存在来表明这一点。

理想情况下，考虑呈现表内容的其他方法，包括将其分解为较小的相关表的集合，这些表不必依赖于`colspan`和`rowspan` 属性。除了帮助使用辅助技术的人员了解表格的内容外，这还可能使那些可能难以理解表格布局。

如果无法拆分表，请使用`id`和`headers` 属性的组合，以编程方式将每个表单元格与该单元格所关联的标题相关联。

- [MDN Tables for visually impaired users](https://wiki.developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Advanced#Tables_for_visually_impaired_users)
- [Tables with multi-level headers • Tables • W3C WAI Web Accessibility Tutorials](https://www.w3.org/WAI/tutorials/tables/multi-level/)
- [H43: Using id and headers attributes to associate data cells with header cells in data tables | Techniques for W3C WCAG 2.0](https://www.w3.org/TR/WCAG20-TECHS/H43.html)
- [Creating a bar chart from a HTML table](http://www.coding-dude.com/wp/html5/bar-chart-html/)

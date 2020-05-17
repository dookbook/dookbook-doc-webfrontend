TOPICS: position property
        top property
        right property
        bottom property
        left property
        z-index property
        float property
        clear property
        display property

# CSS 定位属性

CSS 有三种基本的定位机制：**普通流**、**浮动**和**绝对定位**。

除非专门指定，否则所有框都在普通流中定位。也就是说，普通流中的元素的位置由元素在 (X)HTML 中的位置决定。

块级框从上到下一个接一个地排列，框之间的垂直距离是由框的垂直外边距计算出来。

行内框在一行中水平布置。可以使用水平内边距、边框和外边距调整它们的间距。但是，垂直内边距、边框和外边距不影响行内框的高度。由一行形成的水平框称为行框（Line Box），行框的高度总是足以容纳它包含的
所有行内框。不过，设置 **行高可以增加这个框的高度**。

块级元素的高、宽可自行设置的。行内元素的高和宽不能自行设置。但可以通过`display：inline；`把块元素转化为行内元素；`display：block；`把行内元素转化为块状的元素；
`display：inline-block；` 块级元素和行内元素都可转化为行内块元素。

设置定位机制属性如下：

| 属性 | 描述 |
| :--- | :--- |
| **`position`** | 指定元素在文档中的**定位方式**。**`top`**, **`right`**, **`bottom`** 和 **`left`** 属性则决定了该元素的最终位置。 |
| **`top`** | 定位元素的**上外边距边界**与其包含块**上边界之间的偏移**，非定位元素设置此属性无效。 |
| **`right`** | 定位元素的**右外边距边界**与其包含块**右边界之间的偏移**，非定位元素设置此属性无效。 |
| **`bottom`** | 定位元素**下外边距边界**与其包含块**下边界之间的偏移**，非定位元素设置此属性无效。 |
| **`left`** | 定位元素的**左外边距边界**与其包含块**左边界之间的偏移**，非定位元素设置此属性无效 。|
| **`z-index`** | 指定**定位元素层级**。当**元素之间重叠的时候**，**`z-index`** **较大**的元素会覆盖**较小**的元素在上层进行显示。 |
| **`float`** | 指定**元素应沿其容器**的**左侧**或**右侧浮动**，允许文本和内联元素环绕它。 |
| **`clear`** | 指定**元素清除浮动**。 |
| **`display`** | 设置将元素视为是**块元素**还是**嵌入式元素**以及用于其子元素的布局，例如流布局，网格或`flex`。 |

## `position` 属性值

| 属性值 | 描述 |
| :--- | :--- |
| **`absolute`** | 生成**绝对定位**的元素，相对于 `static` 定位以外的第一个父元素进行定位。|
| **`fixed`** | 生成**固定定位**的元素，相对于浏览器窗口进行定位。|
| **`relative`** | 生成**相对定位**的元素，相对于其正常位置进行定位。|
| **`static`** | 默认值。没有定位，元素出现在正常的流中（忽略 `top`, `bottom`, `left`, `right` 或者 `z-index` 声明）。|
| **`sticky`** | 粘性定位，该定位基于用户滚动的位置。|
|`inherit`|规定应该从父元素继承 `position` 属性的值。|
| `initial`|设置该属性为默认值。|

## `top`, `right`, `right`, `left` 属性值

| 属性值 | 描述 |
| :--- | :--- |
| **`auto`** | 默认值。通过浏览器计算**上右下左**位置。|
| **`%`** | 设置以包含元素的百分比计的**上右下左**位置。可使用负值。|
| `length` | 使用 **px**、**em** 等单位设置元素的**上右下左**位置。可使用负值。|

## `z-index` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`auto`** | **默认**。堆叠顺序与父元素相等。|
| `integer` | `integer`（整型数字）是生成的盒子在当前堆叠上下文中的**堆叠层级**。|

## `float` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`none`** | 默认值。元素**不浮动**，并会显示在其在文本中出现的位置。|
| **`left`** | 元素向**左浮动**。|
| **`right`** | 元素向**右浮动**。|
| **`inline-start`** | 关键字，表明元素必须浮动在其所在块容器的开始一侧，在`ltr`脚本中是左侧，在`rtl`脚本中是右侧。|
| **`inline-end`** | 关键字，表明元素必须浮动在其所在块容器的结束一侧，在`ltr`脚本中是右侧，在`rtl`脚本中是左侧。|

## `clear` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`none`** | 默认值。允许浮动元素出现在两侧。 |
| **`left`** | 清除**左侧浮动**元素。 |
| **`right`** | 清除**右侧浮动**元素。 |
| **`both`** | 清除**左右两侧浮动**元素。 |
| **`inline-start`** | 该关键字表示该元素向下移动以清除其包含块的起始侧上的浮动。即在某个区域的左侧浮动或右侧浮动。 |
| **`inline-end`** | 该关键字表示该元素向下移动以清除其包含块的末端的浮点，即在某个区域的右侧浮动或左侧浮动。 |

## `display` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`none`** | 此元素不会被显示。 |
| **`block`** | 此元素将显示为**块级元素**，此元素前后会带有换行符。 |
| **`inline`** | 默认。此元素会被显示为**内联元素**，元素前后没有换行符。 |
| **`inline-block`** | **行内块元素**。 |
| **`list-item`** | 此元素会作为**列表显示**。 |
| **`run-in`** | 此元素会根据上下文作为**块级元素**或**内联元素**显示。 |
| **`compact`** | CSS 中有值 compact，不过由于缺乏广泛支持，已经从 CSS2.1 中删除。 |
| **`marker`** | CSS 中有值 marker，不过由于缺乏广泛支持，已经从 CSS2.1 中删除。 |
| **`table`** | 此元素会作为**块级表格**来显示（类似 `<table>`），表格前后带有换行符。 |
| **`inline-table`** | 此元素会作为**内联表格**来显示（类似 `<table>`），表格前后没有换行符。|
| **`table-row-group`** | 此元素会作为**一个**或**多个行的分组**来显示（类似 `<tbody>`）。|
| **`table-header-group`** | 此元素会作为**一个**或**多个行的分组**来显示（类似 `<thead>`）。|
| **`table-footer-group`** | 此元素会作为**一个**或**多个行的分组**来显示（类似 `<tfoot>`）。|
| **`table-row`** | 此元素会作为**一个表格行**显示（类似 `<tr>`）。|
| **`table-column-group`** | 此元素会作为**一个**或**多个列的分组**来显示（类似 `<colgroup>`）。|
| **`table-column`** | 此元素会作为**一个单元格列**显示（类似 `<col>`）。|
| **`table-cell`** | 此元素会作为**一个表格单元格**显示（类似 `<td>` 和 `<th>`）。|
| **`table-caption`** | 此元素会作为**一个表格标题**显示（类似 `<caption>`）。|
| **`inherit`** | 规定应该从父元素继承 `display` 属性的值。 |

## 示例

```html
<div class="a">
  <p class="a-child1">这是一段文字A</p>
  <p class="a-child2">这是一段文字B</p>
</div>

<div class="b">
  <p class="b-child1">这是一段文字A</p>
  <p class="b-child2">这是一段文字B</p>
  <p class="b-child3">这是一段文字C</p>
</div>

<div class="c">
  <p class="c-child1">这是一段文字A</p>
  <span class="c-child2">这是一段文字b</span>
</div>
```

```css
.a {
  width: 300px;
  height: 300px;
  position: relative; /* 给父级元素加了相对定义，子元素将相对父级定位 */
  background: #000;
}

.a-child1 {
  background: red;
  width: 300px;
  height: 150px;
  position: absolute; /* 给该元素加了绝对定位，将相对于父级元素定位，如果父级元素没有定位，则相对body定位 */
  left: 0; /* 距离父级元素左边距离为0 */
  top: 20px; /* 距离父级元素上边距离为20px */
}

.a-child2 {
  background: blue;
  width: 200px;
  height: 150px;
  position: absolute;
  right: 0;
  bottom: 20px;
  z-index: 1; /* 给该元素加上层级，它会比 .a-child1 元素层级要高，将会重叠再 .a-child1 元素之上 */
}

.b {
  width: 300px;
  height: 200px;
  background: indianred;
  margin: 20px 0;
}

.b-child1 { /* 给p标签加了左浮动，文字将靠左展示，它将不再占领一行的位置 */
  float: left;
  background: red;
}

.b-child2 { /* 给p标签清除浮动，它不会其它浮动元素的影响 */
  clear: both;
  background: goldenrod;
}

.b-child3 { /* 给p标签加了右浮动，文字将靠右展示，它将不再占领一行的位置 */
  float: right;
  background: blue;
}

.c {
  background: indianred;
  width: 300px;
  height: 200px;
}

.c-child1 {
  display: inline; /* 将会把 <p> 块级元素转化为内联元素 */
  background: khaki;
}

.c-child2 {
  display: block; /* 将 <span> 行内元素转化为块元素 */
  background: lawngreen;
}
```

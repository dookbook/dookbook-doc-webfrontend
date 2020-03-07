TOPICS: list-style property
        list-style-type property
        list-style-image property
        list-style-position property

# CSS 列表属性 (`list-style`)

在HTML中，有两种类型的HTML列表：

- **无序列表** - 列表项标记用**特殊图形**（如**小黑点**、**小方框**等）
- **有序列表** - 列表项的标记有**数字**或**字母**

设置列表项标记属性如下

| 属性 | 描述 |
| :--- | :--- |
| **`list-style`** | 设置**所有的列表**属性, 它是简写属性 |
| **`list-style-type`** | 设置元素**列表项的标记**（例如**数字**，**字母**等样式）|
| **`list-style-image`** | 设置元素**列表标记的图片** |
| **`list-style-position`** | 设置如何**相对于对象的内容绘制列表项标记** |

## `list-style-type` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`none`** | 无标记 |
| **`disc`** | 默认。标记是**实心圆** |
| **`circle`** | 标记是**空心圆** |
| **`square`** | 标记是**实心方块** |
| **`decimal`** | 标记是**数字** |
| **`decimal-leading-zero`** | **0开头的数字标记**。(01, 02, 03, 等。) |
| **`lower-roman`** | **小写罗马数字**(i, ii, iii, iv, v, 等。) |
| **`upper-roman`** | **大写罗马数字**(I, II, III, IV, V, 等。) |
| **`lower-alpha`** | **小写英文字母** (a, b, c, d, e, 等。) |
| **`upper-alpha`** | **大写英文字母** (A, B, C, D, E, 等。) |
| **`lower-greek`** | **小写希腊字母**(alpha, beta, gamma, 等。) |
| **`lower-latin`** | **小写拉丁字母**(a, b, c, d, e, 等。) |
| **`upper-latin`** | **大写拉丁字母**(A, B, C, D, E, 等。) |
| **`hebrew`** | **传统的希伯来编号**方式 |
| **`armenian`** | **传统的亚美尼亚编号**方式 |
| **`georgian`** | **传统的乔治亚编号**方式(an, ban, gan, 等。) |
| **`cjk-ideographic`** | **简单的表意数字** |
| **`hiragana`** | 标记是: **a, i, u, e, o, ka, ki** 等。（日文片假名） |
| **`katakana`** | 标记是: **A, I, U, E, O, KA, KI** 等。（日文片假名） |
| **`hiragana-iroha`** | 标记是: **i, ro, ha, ni, ho, he, to** 等。（日文片假名） |
| **`katakana-iroha`** | 标记是: **I, RO, HA, NI, HO, HE, TO** 等。（日文片假名） |

## `list-style-image` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **URL** | 图像的路径。|
| **`none`** | 默认。无图形被显示。|

## `list-style-position` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`inside`** | 列表项目标记放置在文本以内，且环绕文本根据标记对齐。|
| **`outside`** | 默认值。保持标记位于文本的左侧。列表项目标记放置在文本以外，且环绕文本不根据标记对齐。|

## 示例

!!! warn "注意"
    **`list-style-type`** 和 **`list-style-image`** 同时只能生效一个

```html
List 1
<ul class="one">
  <li>List Item1</li>
  <li>List Item2</li>
  <li>List Item3</li>
</ul>
List 2
<ol class="two">
  <li>List Item A</li>
  <li>List Item B</li>
  <li>List Item C</li>
</ol>
```

```css
ul li, ol li {
  border: 1px solid #000;
}

ul {
  /* 表示列表项以图片标记，并放置在左侧文本内 */
  list-style: url('sqpurple.gif') inside;
}

ol {
  /* 表示列表项以数字标记 */
  list-style-type: decimal;

  /* 表示列表项标记放置在左侧文本以外 */
  list-style-position: outside;
}
```

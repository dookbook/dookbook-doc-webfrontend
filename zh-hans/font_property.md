TOPICS: font property
        font-style property
        font-variant property
        font-weight property
        font-size property
        font-family property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 属性: `font`

**`font`** 属性可以用来作为 **`font-style`**, **`font-variant`**, **`font-weight`**, **`font-size`**, **`line-height`**
和 **`font-family`** 属性的简写，或将元素的字体设置为系统字体。

## CSS 属性: `font-style`

**`font-style`** CSS 属性允许你选择 `font-family` 字体下的 `italic` 或 `oblique` 样式。

| 属性值 | 说明 |
| :--- | :--- |
| `normal` | 选择 `font-family` 的常规字体。|
| `italic` | 选择斜体，如果当前字体没有可用的斜体版本，会选用倾斜体（oblique ）替代。|
| `oblique` | 选择倾斜体，如果当前字体没有可用的倾斜体版本，会选用斜体（ italic ）替代。|

## CSS 属性: `font-variant`

**`font-variant`** 属性设置**小型大写字母的字体显示文本**，这意味着所有的小写字母均会被转换为大写，但是所有使用小型大写字体的字母与其余文本相比，其字体尺寸更小

| 属性值 | 说明 |
| :--- | :--- |
| `normal` | 默认值。浏览器会显示一个标准的字体。|
| `small-caps` | 浏览器会显示小型大写字母的字体。|
| `inherit` | 规定应该从父元素继承 `font-variant` 属性的值。|

## CSS 属性: `font-weight`

CSS **`font-weight`** 属性指定了**字体的粗细程度**。一些字体只提供 `normal` 和 `bold` 两种值。

| 属性值 | 说明 |
| :--- | :--- |
| `bold` | 加粗。与`700`等值。|
| `normal` | 正常粗细。与`400`等值。|
| `100`, `200`, `300`, `400`, `500`, `600`, `700`, `800`, `900` | 数值化的规定字体粗细程度的方式，提供了除了 `normal` 和 `bold` 之外更多的值。|
| `lighter` | 定义更细的字符。|
| `bolder` | 定义更粗的字符。|

## CSS 属性: `font-size`

CSS **`font-size`** 属性指定**字体的大小**。因为该属性的值会被用于计算em和ex长度单位，定义该值可能改变其他元素的大小。

| 属性值 | 说明 |
| :--- | :--- |
| `xx-small`,`x-small`,`small`,`medium`,`large`,`x-large`,`xx-large` | 把字体的尺寸设置为不同的尺寸，从 `xx-small` 到 `xx-large`。<br>默认值：`medium`。|
| `smaller` | 设置为比父元素更小的尺寸。|
| `larger` | 设置为比父元素更大的尺寸。|
| `length` | 设置为一个固定的值。|
| `%` | 设置为基于父元素的一个百分比值。|
| `inherit` | 规定应该从父元素继承字体尺寸。|

## CSS 属性: `font-family`

CSS **`font-family`** 属性允许您通过给定一个有先后顺序的，由字体名或者字体族名组成的列表来为选定的元素设置字体。

属性的值用**逗号**隔开。浏览器会选择列表中第一个该计算机上有安装的字体，或者是通过 `@font-face` 指定的可以直接下载的字体。

| 属性值 | 说明 |
| :--- | :--- |
| `family-name`,`generic-family` | 用于某个元素的字体族名称或/及类族名称的一个优先表。<br>默认值：取决于浏览器 |
| `inherit` | 规定应该从父元素继承字体系列 |

## 示例: 使用 `font` 属性

```css
p.ex1 {
  font: 15px arial, sans-serif;
}

p.ex2 {
  font: italic bold 12px/30px Georgia, serif;
}
```

```html
<p class="ex1">This is a paragraph. This is a paragraph. This is a paragraph. This is a paragraph. This is a paragraph. This is a paragraph. This is a paragraph. This is a paragraph.</p>
<p class="ex2">This is a paragraph. This is a paragraph. This is a paragraph. This is a paragraph. This is a paragraph. This is a paragraph. This is a paragraph. This is a paragraph.</p>
```

## 示例: 使用 `font-style` 属性

```css
.normal {
  font-style: normal;
}

.italic {
  font-style: italic;
}

.oblique {
  font-style: oblique;
}
```

## 示例: 使用 `font-variant` 属性

```css
p.normal { font-variant: normal; }
p.small { font-variant: small-caps; }
```

```html
<p class="normal">My name is Hege Refsnes.</p>
<p class="small">My name is Hege Refsnes.</p>
```

## 示例: 使用 `font-weight` 属性

```css
/* Set paragraph text to be bold. */
p {
  font-weight: bold;
}

/* Set div text to two steps darker than
   normal but less than a standard bold. */
div {
  font-weight: 600;
}

/* Sets text enclosed within span tag
   to be one step lighter than the parent. */
span {
  font-weight: lighter;
}
```

```html
<p>
  Alice was beginning to get very tired of sitting by her sister on the
  bank, and of having nothing to do: once or twice she had peeped into the
  book her sister was reading, but it had no pictures or conversations in
  it, 'and what is the use of a book,' thought Alice 'without pictures or
  conversations?'
</p>

<div>I'm heavy<br/>
  <span>I'm lighter</span>
</div>
```

## 示例: 使用 `font-size` 属性

```css
h1 { font-size: 250%; }
h2 { font-size: 200%; }
p { font-size: 100%; }
```

```html
<h1>This is heading 1</h1>
<h2>This is heading 2</h2>
<p>This is a paragraph.</p>
```

## 示例: 使用 `font-family` 属性

```css
p.serif { font-family: "Times New Roman", Times, serif; }
p.sansserif { font-family: Arial, Helvetica, sans-serif; }
```

```html
<h1>CSS font-family</h1>
<p class="serif">这一段的字体是 Times New Roman </p>
<p class="sansserif">这一段的字体是 Arial.</p>
```

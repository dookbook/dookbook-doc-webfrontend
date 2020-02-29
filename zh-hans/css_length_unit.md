TOPICS: CSS length unit
        px
        em
        rem
        %
        cm
        mm
        ch
        ex
        vw
        vh
        vmin
        vmax
        in
        pt
        pc

# CSS 长度单位

CSS 长度单位是由 **`px`**, **`em`**, **`rem`**, **`%`**, **`cm`**, **`mm`**, **`ch`**, **`ex`**, **`vw`**,
**`vh`**, **`vmin`**, **`vmax`**, **`in`**, **`pt`**, **`pc`** 所表示的。

有两种类型的长度单位：**相对**和**绝对**。

一些设置 CSS 长度的属性有 [*`width`*](/zh-hans/webfrontend/width_property), [*`height`*](/zh-hans/webfrontend/height_property),
[*`margin`*](/zh-hans/webfrontend/margin_property),
[*`padding`*](/zh-hans/webfrontend/padding_property),
[*`font-size`*](/zh-hans/webfrontend/font-size_property) 等。

如果长度值为 **`0`**，**则可以省略单位**，且**数字**与**单位**之间**不能出现空格**

## CSS 长度单位 `px`

**`px` 像素**是绝对长度单位，它的大小是根据用户屏幕显示器的分辨率决定的（因此不同的设备显示相同的像素值也可能会有不同的结果）

```css
h1 { font-size: 50px; }
h2 { font-size: 30px; }

p {
  font-size: 15px;
  line-height: 20px;
}
```

```html
<h1>这是一个标题 1</h1>
<h2>这是一个标题 2</h2>
<p>这是一个段落。</p>
<p>这是另一个段落。</p>
```

## CSS 长度单位 `em`

**`em`** 是相对长度单位，是相对于父级元素的字体尺寸应用。一般浏览器字体大小默认为`16px`, 则 `1em == 16px`。

下列 [`<html>`](/zh-hans/webfrontend/<html>)根元素字体为 `16px`，而 `class` 为 `"box1"` 的字体是 `18px`，
所以 `class` 为 `"box"` 的 `1em == 16px`;
而 `class` 为 `"box1"` 里面的 [`<p>`](/zh-hans/webfrontend/<p>) 元素的 `1em == 18px`

```css
html { font-size: 16px; }
.box { font-size: 1em; }
.box1 { font-size: 18px; }
.box1 p { font-size: 1em; }
```

```html
<div class="box">这是一段文字</div>

<div class="box1">
  <p>这是一段文字</p>
  <p>这是一段文字</p>
  <p>这是一段文字</p>
</div>
```

## CSS 长度单位 `rem`

**`rem`** 是相对长度单位，相对于应用[`<html>`](/zh-hans/webfrontend/<html>)根元素的字体尺寸。如果根元素没有设定，则相对于浏览器的默认字体尺寸，
一般浏览器字体大小默认为`16px`, 则 `1em == 16px`。

下列不管父级元素定义字体是多少，`rem` 都是相对于 [`<html>`](/zh-hans/webfrontend/<html>)根元素来定义，所以 `1rem` 永远等于 `16px`

```css
html { font-size: 16px; }
.box { font-size: 1rem; }
.box1 { font-size: 18px; }
.box1 p { font-size: 1rem; }
```

```html
<div class="box">这是一段文字</div>

<div class="box1">
  <p>这是一段文字</p>
  <p>这是一段文字</p>
  <p>这是一段文字</p>
</div>
```

## CSS 相对长度单位 `%`

**`%` 百分比** 是相对长度单位，一般用来继承父级元素的宽和高，或者根据浏览器的宽和高来自适应，比如：如果想设置某个元素的宽度的背景色跟着浏览器的变化而变化，这个 `%` 单位将很有用

```css
div {
  height: 150px;
  width: 100px;
  background: red;
}

p {
  height:100%;
  width:100%;
  background: blue;
}
```

```html
<p>CSS 相对长度单位 %</p>
```

## CSS 长度单位 `cm`

**`cm` 厘米** 是绝对长度单位。

```css
h1 {font-size: 1.2cm;}
h2 {font-size: 1cm;}
```

```html
<h1>这是一个标题 1</h1>
<h2>这是一个标题 2</h2>
```

## CSS 长度单位 `mm`

**`mm` 毫米** 是绝对长度单位。

```css
h1 {font-size: 15mm;}
h2 {font-size: 10mm;}
```

```html
<h1>这是一个标题 1</h1>
<h2>这是一个标题 2</h2>
```

## CSS 长度单位 `ch`

**`ch`** 是相对长度单位，定义**数字 0 的宽度**, 例如: **`1ch`** 等于 **一个数字 0 的宽度**。

下列 [`<div>`](/zh-hans/webfrontend/<div>) 元素的背景色只显示**5个数字 0 的宽度**

```css
div {
  width: 5ch;
  background: #ccc;
}
```

```html
<div>0000000</div>
```

## CSS 长度单位 `ex`

**`ex`** 相对长度单位。相对于字符 **"x"** 的高度。通常为字体高度的一半。

```css
h1 {
  margin: 10px 0;
  font-size: 16px;
}

.x {
  overflow: hidden;
  height: 1ex;
  background: #aaa;
}
```

```html
<h1>定义一条与字母x高度相同的线：</h1>
<div>xxxx</div>
<div class="x"></div>
```

## CSS 长度单位 `vw`

**`vw`** 相对于视口的宽度。视口被均分为`100`单位的`vw`, 相对长度单位

```css
h1 { font-size: 8vw; }
```

```html
<h1>相对于viewport宽度大小的文字</h1>
```

如果视口的宽度是 `200mm`，那么上述代码中[`<h1>`](/zh-hans/webfrontend/<h1>)元素的字号将为 `16mm`，即 `(8x200)/10`

## CSS 长度单位 `vh`

**`vh`** 相对于视口的高度。视口被均分为`100`单位的`vh`, 相对长度单位

```css
h1 { font-size: 8vh; }
```

```html
<h1>相对于viewport高度大小的文字</h1>
```

如果视口的高度是 `200mm`，那么上述代码中[`<h1>`](/zh-hans/webfrontend/<h1>)元素的字号将为 `16mm`，即 `(8x200)/100`

## CSS 长度单位 `vmin`

**`vmin`** 是相对长度单位，是 *`vw`* 和 *`vh`* 中较小的那个。

```css
h1 {
  font-size: 15vmin;
}
```

```html
<h1>Hello</h1>

<p>试着缩小或放大浏览器 高度和宽带 来查看 h1 的字体大小如何改变。</p>
```

## CSS 长度单位 `vmax`

**`vmax`** 是相对长度单位，*`vw`*和*`vh`*中较大的那个。

```css
h1 {
  font-size: 15vmax;
}
```

```html
<h1>Hello</h1>

<p>试着缩小或放大浏览器（高度和宽带）来查看 h1 的字体大小如何改变。</p>
```

## CSS 长度单位 `in`

**`in` 英寸** (Inches) 是绝对长度单位

```css
h1{margin:10px 0;font-size:16px;}
ul{margin:0;padding:0;list-style:none;}
li{margin-top:8px;background:#ccc;}
.in{width:1in;}
.pt{width:72pt;}
.pc{width:6pc;}
.px{width:96px;}
.cm{width:2.54cm;}
.mm{width:25.4mm;}
```

```html
<h1>单位转换对比：</h1>
<ul>
  <li class="in">1in</li>
  <li class="pt">72pt</li>
  <li class="pc">6pc</li>
  <li class="px">96px</li>
  <li class="cm">2.54cm</li>
  <li class="mm">25.4mm</li>
</ul>
<p>1in = 2.54cm = 25.4 mm = 72pt = 6pc = 96px</p>
```

## CSS 长度单位 `pt`

**`pt`** (Points) 是绝对长度单位

```css
h1 {font-size: 50pt;}
h2 {font-size: 25pt;}
p {
    font-size: 15pt;
    line-height: 25pt;
}
```

```html
<h1>这是一个标题 1</h1>
<h2>这是一个标题 2</h2>
<p>这是一个段落。</p>
<p>这是另一个段落。</p>
```

## CSS 长度单位 `pc`

**`pc`** (Picas) 是绝对长度单位，相当于我国新四号铅字的尺寸。

```css
h1 {font-size: 4.5pc;}
h2 {font-size: 3pc;}
p {
    font-size: 1.5pc;
    line-height: 3pc;
}
```

```html
<h1>这是一个标题 1</h1>
<h2>这是一个标题 2</h2>
<p>这是一个段落。</p>
<p>这是另一个段落。</p>
```

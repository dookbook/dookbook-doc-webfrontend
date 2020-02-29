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

| 单位 | 描述 |
| :--- | :--- |
| **`px`** | **像素**是绝对长度单位，它的大小是根据用户屏幕显示器的分辨率决定的（因此不同的设备显示相同的像素值也可能会有不同的结果）|
| **`em`** | 是相对长度单位，是相对于父级元素的字体尺寸应用。一般浏览器字体大小默认为`16px`, 则 `1em == 16px` |
| **`rem`** | 是相对长度单位，相对于应用[`<html>`](/zh-hans/webfrontend/<html>)根元素的字体尺寸。如果根元素没有设定，则相对于浏览器的默认字体尺寸，一般浏览器字体大小默认为`16px`, 则 `1rem == 16px`。|
| **`%`** | **百分比**是相对长度单位，一般用来继承父级元素的宽和高，或者根据浏览器的宽和高来自适应，比如：如果想设置某个元素的宽度的背景色跟着浏览器的变化而变化，这个 `%` 单位将很有用 |
| **`cm`** | **厘米**是绝对长度单位。|
| **`mm`** | **毫米**是绝对长度单位。|
| **`in`** | **英寸** (Inches) 是绝对长度单位 |
| **`pt`** | **磅** (Points) 是绝对长度单位 |
| **`pc`** | **点** (Picas) 是绝对长度单位，相当于我国新四号铅字的尺寸。|
| **`ch`** | 是相对长度单位，定义**数字 0 的宽度**, 例如: **`1ch`** 等于 **一个数字 0 的宽度** |
| **`ex`** | 相对长度单位。相对于字符 **"x"** 的高度。通常为字体高度的一半。|
| **`vw`** | 相对于视口的宽度。视口被均分为`100`单位的`vw`, 相对长度单位 |
| **`vh`** | 相对于视口的高度。视口被均分为`100`单位的`vh`, 相对长度单位 |
| **`vmin`** | 是相对长度单位，是 *`vw`* 和 *`vh`* 中较小的那个。|
| **`vmax`** | 是相对长度单位，*`vw`* 和 *`vh`* 中较大的那个。|

## 示例: 单位换算

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

## 示例: `rem` 和 `em`

```css
html { font-size: 16px; }
.box p { font-size: 1em; }
.box span { font-size: 1rem; }
.box1 { font-size: 22px; }
.box1 p { font-size: 1em; }
.box1 span { font-size: 1rem; }
```

```html
<div class="box">
  <p>这是段文字定义的是1em</p> <!-- 父级元素没有定义字体大小，所以这个段落的字体是 16px，因为它顺势继承了父级的父级设置的字体小大 -->
  <span>这是段文字定义的是1rem</span> <!-- 这段文字是字体也是16px, 因为根元素设置了16px -->
</div>

<div class="box1">
  <p>这是段文字定义的是1em</p><!-- 这个段落的字体是 22px，因为 em 相对父级元素设置的字体小大而设定的 -->
  <span>这是段文字定义的是1rem</span><!-- 这段文字是字体仍然是16px, 因为 rem 永远只相对于根元素设定 -->
</div>
```

## 示例: `ch`

```css
div {
  width: 5ch;
  background: #ccc;
}
```

```html
<!-- <div>元素的背景色只显示**5个数字 0 的宽度 -->
<div>0000000</div>
```

## 示例: `ex`

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

## 示例: `vw` 和 `vh`

```css
h1 { font-size: 8vw; }
h2 { font-size: 8vh; }
```

```html
<!-- 如果视口的宽度是 200mm，那么上述代码中<h1>元素的字号将为 16mm，即 (8x200)/10 -->
<h1>相对于viewport宽度大小的文字</h1>

<!-- 如果视口的高度是 200mm，那么上述代码中<h2>元素的字号将为 16mm，即 (8x200)/10 -->
<h2>相对于viewport高度大小的文字</h2>
```

## 示例: `vmin` 和 `vmax`

```css
h1 {
  font-size: 15vmin;
}

h2 {
  font-size: 15vmax;
}
```

```html
<h1>Hello</h1>
<p>试着缩小或放大浏览器 高度和宽带 来查看 h1 的字体大小如何改变。</p>

<h2>Hello</h2>
<p>试着缩小或放大浏览器（高度和宽带）来查看 h2 的字体大小如何改变。</p>
```

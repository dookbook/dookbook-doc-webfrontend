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
AUTHORS: Li Yun; leven.cn@gmail.com; github:leven-cn

# CSS 长度单位

CSS 长度单位有两种类型：**相对长度**和**绝对长度**。**绝对长度单位**是一个固定的值，它反应一个真实的物理尺寸。绝对长度单位视输出介质而定，不依赖于环境（显示器、分辨率、操作系统等）。**相对长度单位**指定了一个长度相对于另一个长度的属性。对于不同的设备，相对长度更适用。

**数字**与**单位**之间**不能出现空格**。如果长度值为 **`0`**，**则可以省略单位**。

## 绝对长度单位

| 单位 | 描述 |
| :--- | :--- |
| **`cm`** | **厘米** |
| **`mm`** | **毫米** |
| **`in`** | **英寸** (**Inches**) |
| **`pt`** | **磅** (**Points**) |
| **`pc`** | **点** (**Picas**) 相当于我国新四号铅字的尺寸。 |
| **`px`** | **像素**是根据屏幕显示器的分辨率决定的（因此不同的设备显示相同的像素值也可能会有不同的结果）|

像素或许被认为是最好的"设备像素"，而这种像素长度和你在显示器上看到的文字屏幕像素无关。`px`实际上是一个按角度度量的单位。

### CSS绝对长度单位换算

1in = 2.54cm = 25.4mm = 72pt = 6pc = 96px

## 相对长度单位

| 单位 | 描述 |
| :--- | :--- |
| **`ch`** | （不常用）相对于**数字 *`0`* 的宽度**。|
| **`ex`** | （不常用）相对于**字符 *`x`* 的高度**。通常为字体高度的一半。|
| **`%`** | **百分比**一般用来继承父级元素的宽和高，或者根据浏览器的宽和高来自适应。 |
| **`em`** | 相对于*父级元素*的字体尺寸。一般浏览器字体大小默认为 *`16px`*, 则 `1em == 16px` |
| **`rem`** | 相对于[*`<html>`*](/zh-hans/webfrontend/<html>)根元素的字体尺寸。如果根元素没有设定，则相对于浏览器的默认字体尺寸，一般浏览器字体大小默认为 *`16px`*, 则 `1rem == 16px`。|
| **`vw`** | 相对于**视窗的宽度**。视窗被均分为`100`单位的`vw` |
| **`vh`** | 相对于**视窗的高度**。视窗被均分为`100`单位的`vh` |
| **`vmin`** | 是 *`vw`* 和 *`vh`* 中较小的那个。|
| **`vmax`** | 是 *`vw`* 和 *`vh`* 中较大的那个。|

### 相对长度单位示例

```html
<div>
  <p>这是一个段落 A</p>
  <p class="b">这是一个段落 B</p>
  <p class="c">xx<span>x</span></p>
  <p class="d">00<span>0</span></p>
  <p class="e">这是一个段落 E</p>
  <p class="f">这是一个段落 F</p>
</div>
```

```css
/* 一般浏览器字体大小默认为 16px */
html { font-size: 16px; }

/* 使用绝对和相对长度单位定义字体大小 */
p.b { font-size: 0.5cm; }  /* 使用绝对长度单位 cm 厘米 */
p.c > span { font-size: 2ex; }  /* 相当于2个字母x的高度 */
p.d > span { font-size: 2ch; }  /* 相当于2个数字0的宽度 */

/* rem 和 em 区别 */
/* 不管父级元素定义字体是多少，`rem`都是相对于<html>根元素来定义 */
div { font-size: 10px; }  /* 父元素字体大小 */
p.e { font-size: 1.5em; }  /* 相当于1.5个父元素字体大小，即 1.5 x 10px = 15px (1em=10px)*/
p.f { font-size: 1.5rem; }  /* 相当于1.5个<html>元素字体大小，即 1.5 x 16px = 24px (1rem=16px) */

/* % 百分比长度单位示例 */
div {  /* 父元素使用绝对长度单位 */
  height: 150px;
  width: 150px;
  background: black;
}
p {  /* 子元素使用相对长度单位，相对于父元素 */
  height: 80%;
  width: 80%;
  background: red;
}
```

### 视窗单位示例

```html
<h1>Hello</h1>
<h2>Hello</h2>
<h3>Hello</h3>
<h4>Hello</h4>
```

```css
/* vw 和 vh 长度单位示例 */
/* 例如: 浏览器高度950px，宽度为1920px, 1vh = 950px/100 = 9.5px，1vw = 1920px/100 = 19.2px。 */
h1 { font-size: 20vw; } /* 20vw 等于20/100的视窗宽度 */
h2 { font-size: 20vh; } /* 20vh 等于20/100的视窗高度 */

/* vmin 和 vmax 长度单位示例 */
/*
例如:浏览器宽度为1100px、高度为700px，1vmin = 700px/100 = 7px，1vmax = 1100/100 = 11px。
    浏览器宽度为800px，高度为1080px，1vmin = 800px/100 = 8px，1vmax = 1080px/100 = 10.8px
*/
h3 { font-size: 15vmin; } /* 试着缩小或放大浏览器（高度和宽度）来查看 h3 的字体大小如何改变。 */
h4 { font-size: 15vmax; } /* 试着缩小或放大浏览器（高度和宽度）来查看 h4 的字体大小如何改变。 */
```

## Browser compatibility

The numbers in the table below indicate the minimum browser version that supports this length unit.

| Unit of length | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
| `em`, `ex`, %, `px`, `cm`, `mm`, `in`, `pt`, `pc` | 1.0 | 1.0 | 1.0 |
| `ch`| 27.0| 1.0 | 7.0 |
| `rem` | 4.0 | 3.6 | 4.1 |
| `vh`, `vw` | 20.0 | 19.0 | 6.0 |
| `vmin` | 20.0 | 19.0 | 6.0 |
| `vmax` | 26.0 | 19.0 | 不支持 |

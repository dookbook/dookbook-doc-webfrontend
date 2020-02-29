TOPICS: margin property
        margin-top property
        margin-right property
        margin-bottom property
        margin-left property
AUTHORS: zhenfan.yu; fanerge@qq.com; github:fanerge
         卢思侗; wowlusitong@gmail.com; github:wowlusitong
         Sebastian Zartner; SebastianZ@github.com; github:SebastianZ
         Sphinx; SphinxKnight@github.com; github:SphinxKnight
         Florian Scholz; fscholz@mozilla.net; mdn:fscholz
         杜维康; VictorDu@mozilla.net; mdn:VictorDu
         Safeer Rana; Prinz_Rana@mozilla.net; mdn:Prinz_Rana
         John Cido; johncido@mozilla.net; mdn:johncido

# CSS 属性: `margin`

**`margin`** 属性为给定元素设置**所有四个（上下左右）方向的外边距**属性。这是四个外边距属性设置的简写。四个外边距属性设置分别是： **`margin-top`**, **`margin-right`**,
**`margin-bottom`** 和 **`margin-left`**。指定的外边距允许为负数。

`margin` 的 **`top`** 和 **`bottom`** 属性对非替换内联元素无效，例如 [*`<span>`*](/zh-hans/webfrontend/<span>) 和 [*`<code>`*](/zh-hans/webfrontend/<span>)。

## 属性值

接受1~4个可选参数，每个参数取值如下：

- **只有一个** 值时，这个值会被指定给全部的 **四个边**.
- **两个** 值时，第一个值被匹配给 **上和下**, 第二个值被匹配给 **左和右**.
- **三个** 值时，第一个值被匹配给 **上**, 第二个值被匹配给 **左和右**, 第三个值被匹配给 **下**.
- **四个** 值时，会依次按 **上、右、下、左** 的顺序匹配 (即顺时针顺序).

| 属性值 | 说明 |
| :--- | :--- |
| length | 指定一个固定的宽度。可以为负数。|
| **`%`** | 相对于该元素的包含块的宽度（相对于该块的百分比）。该值可以为负数。|
| **`auto`** | 浏览器会自动选择一个合适的`margin`来应用。它可以用于将一个块居中。<br>比如: `div { width:50%;  margin:0 auto; }` 会把这个`div`容器水平居中。|

## CSS 属性: `margin-top`

**`margin-top`** 属性用来设置**元素的顶部外边距**，你也可以使用负值。

## CSS 属性: `margin-right`

**`margin-right`** 属性设置与**元素相关联的盒子模型的右外边距**。这个值可以为负值。

竖直排列相邻的两个盒子模型的外边距会重叠，称为 margin collapsing.

## CSS 属性: `margin-bottom`

CSS的 **`margin-bottom`** 属性用于设置**元素的底部外边距**，允许设置负数值。一个正数值将让它相对于正常流与邻近块更远，而负数值将使得更近。

## CSS 属性: `margin-left`

**`margin-left`** CSS属性设置元素的**左侧空白区域**。 正值会使它离邻居更远，而负值会使它更近。

## 示例

```html
<div class="ex1">
  margin:     auto;
  background: gold;
  width:      66%;
</div>
<div class="ex2">
  margin:     20px 0 0 -20px;
  background: gold;
  width:      66%;
</div>
```

```css
.ex1 {
  margin: auto;
  background: gold;
  width: 66%;
}
.ex2 {
  margin: 20px 0px 0 -20px;
  background: gold;
  width: 66%;
}
```

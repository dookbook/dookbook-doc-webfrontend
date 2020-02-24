TOPICS: line-height property

# CSS 属性: `line-height`

CSS **`line-height`** 属性用于设置多行元素的空间量，如多行文本的间距。对于块级元素，它指定元素行盒（line boxes）的最小高度。对于非替代的 `inline` 元素，
它用于计算行盒（line box）的高度。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`normal`** | 默认。设置合理的行间距 |
| number | 设置数字，此数字会与当前的字体尺寸相乘来设置行间距 |
| length | 设置固定的行间距 |
| **`%`** | 基于当前字体尺寸的百分比行间距 |

## 基本示例

```css
/* 理论上，以下所有规则拥有相同的行高 */

div { line-height: 1.2;   font-size: 10pt; }   /* 无单位数值 number/unitless */
div { line-height: 1.2em; font-size: 10pt; }   /* 长度 length */
div { line-height: 120%;  font-size: 10pt; }   /* 百分比 percentage */
div { font: 10pt/1.2  Georgia,"Bitstream Charter",serif; } /* font 简写属性 font shorthand */
```

为了简便，可以通过 **`font`** 简写来设置 `line-height`，但这要求在使用该简写属性时同时设置 **`font-family`** 属性。

## 推荐在设置 `line-height` 时使用无单位数值

这个示例说明了为什么给 `line-height` 赋值时使用 `<number>` 值比使用 `<length>` 更好。我们会到用两个 [`<div>`](/zh-hans/webfrontend/<div>)
元素。第一个 `div` 为绿色边框，使用无单位的 `line-height`值。第二个 `div` 带红色边框，使用 `em` 定义 `line-height` 的值。

```css
.green {
  line-height: 1.1;
  border: solid limegreen;
}

.red {
  line-height: 1.1em;
  border: solid red;
}

h1 {
  font-size: 30px;
}

.box {
  width: 18em;
  display: inline-block;
  vertical-align: top;
  font-size: 15px;
}
```

```html
<div class="box green">
 <h1>Avoid unexpected results by using unitless line-height.</h1>
  length and percentage line-heights have poor inheritance behavior ...
</div>

<div class="box red">
 <h1>Avoid unexpected results by using unitless line-height.</h1>
  length and percentage line-heights have poor inheritance behavior ...
</div>

<!-- The first <h1> line-height is calculated from its own font-size   (30px × 1.1) = 33px  -->
<!-- The second <h1> line-height results from the red div's font-size  (15px × 1.1) = 16.5px,  probably not what you want -->
```

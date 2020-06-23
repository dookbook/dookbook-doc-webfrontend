TOPICS: font-size-adjust property

# CSS 属性: `font-size-adjust`

CSS属性 **`font-size-adjust`** 定义字体大小**应取决于小写字母**，而不是大写字母。在字体较小时，字体的可读性主要由小写字母的大小决定，通过此选项即可进行调整。

当 [**`font-family`**](/zh-hans/webfrontend/font-family_property) 的首选字体不可用时，如果备选字体的尺寸比（小写字母的大小与字体大小的比）有较大的差别时，可读性可能会成为一大问题。

为了兼容于不支持 **`font-size-adjust`** 的浏览器，该属性的值应该被定义为 [**`font-size`**](/zh-hans/webfrontend/font-size_property)
的值所要乘的系数。这意味着定义的值应该为首选字体的尺寸比。

例如：样式表这样定义的真实作用是定义小写字母的大小应该为`7px`高 (`0.5 × 14px`)。

```css
font-size: 14px;
font-size-adjust: 0.5;
```

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`none`** | 仅根据 **`font-size`** 属性决定字体大小。|
| **number** | 根据使小写字母大小（根据字体的x-height--西文字体设计中的基线与主线的距离--决定）为该值乘以[**`font-size`**](/zh-hans/webfrontend/font-size_property)的结果定义字体。<br><br>数字应为[**`font-family`**](/zh-hans/webfrontend/font-family_property)的首选字体的尺寸比（x-height和字体大小的比）。这意味着当首选字体可用时，不论浏览器是否支持 **`font-size-adjust`**，都会显示文字为[**`font-size`**](/zh-hans/webfrontend/font-size_property)的大小。|

## 示例

```css
p {
  font: 12px Verdana, "DejaVu Sans", sans-serif;
  font-size-adjust: 0.58;
}
```

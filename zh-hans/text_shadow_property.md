TOPICS: text-shadow property
AUTHORS: Sebastian Zartner; SebastianZ@github.com; github:SebastianZ
         Dong WEI; FredWe@mozilla.net; mdn:FredWe
         Teoli; teoli@mozilla.net; mdn:teoli
         天赋创新; tonghao_xjtu@qq.com; github:tfcx-th
         Ivan Yan; yanxyz@github.com; github:yanxyz

# CSS 属性: `text-shadow`

`text-shadow`为文字添加阴影。可以为文字与 `text-decorations` 添加多个阴影，阴影值之间用逗号隔开。

当阴影大于一个时要用逗号区别开阴影之间的参数

每个阴影都有两到三个`<length>`参数 ， 以及一个与阴影颜色相关的`<color>`参数 。 前两个`<length>`参数，是以“文字中心”为原点的坐标轴，分别为x轴 `<offset-x>`
和y轴 `<offset-y>` 的值； 如果有第三个`<length>`参数，则第三个数值为形成阴影效果的半径的数值 `<blur-radius>` 。

当所给的阴影大于一个时，阴影应用的顺序为从前到后, 第一个指定的阴影在顶部.

这个属性同时适用于 `::first-line` 以及 `::first-letter` 伪元素.

## 属性值

| 属性值 | 描述 |
| :--- | :--- |
| `<color>` | 可选。可以在偏移量之前或之后指定。如果没有指定颜色，则使用UA（用户代理）自行选择的颜色。|
| `<offset-x> <offset-y>` | 必选。这些长度值指定阴影相对文字的偏移量。`<offset-x>` 指定水平偏移量，若是负值则阴影位于文字左边。`<offset-y>` 指定垂直偏移量，若是负值则阴影位于文字上面。如果两者均为`0`，则阴影位于文字正后方（如果设置了 `<blur-radius>` 则会产生模糊效果)。可用单位请查看 `<length>`。|
| `<blur-radius>` | 可选。这是 `<length>` 值。如果没有指定，则默认为`0`。值越大，模糊半径越大，阴影也就越大越淡（wider and lighter）。|

## 示例

```css
.red-text-shadow {
  text-shadow: red 0 -2px;
}
```

```html
<p class="red-text-shadow">
   Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo
   inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo.
</p>
```

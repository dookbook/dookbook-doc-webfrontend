TOPICS: text-indent property
AUTHORS: Sebastian Zartner; SebastianZ@github.com; github:SebastianZ
         彼術向; Mookiepiece@github.com; github:Mookiepiece
         Florian Scholz; fscholz@mozilla.net; mdn:fscholz
         Teoli; teoli@mozilla.net; mdn:teoli

# CSS 属性: `text-indent`

`text-indent` 属性规定了一个元素**首行文本内容之前应该有多少水平空格**。水平空格是块级包含元素的内容盒子的左边(对于从右向左布局来说是右边).

## 属性值

| 属性值 | 描述 |
| :--- | :--- |
| `length` | 定义固定的缩进。默认值：`0`。|
| `%` | 定义基于父元素宽度的百分比的缩进。|

## 示例

```css
p {
  text-indent: 5em;
  background: powderblue;
}
```

```html
<p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy
    nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat.</p>
<p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy
    nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat.</p>
```

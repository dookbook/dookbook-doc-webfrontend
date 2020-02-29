TOPICS: padding property
        padding-top property
        padding-right property
        padding-bottom property
        padding-left property
AUTHORS: Sebastian Zartner; SebastianZ@github.com; github:SebastianZ
         Dong WEI; FredWe@mozilla.net; mdn:FredWe
         rxliuli; rxliuli@gmail.com; github:rxliuli
         ZCDC_Ren; renzw@zzes1314.cn; github:klren0312
         夏凌晨; xgqfrms@mozilla.net; mdn:xgqfrms
         Florian Scholz; fscholz@mozilla.net; mdn:fscholz
         Teoli; teoli@mozilla.net; mdn:teoli
         Cici Hu; Huooo@mozilla.net; mdn:Huooo

# CSS 属性: `padding`

**`padding`** 属性设置一个**元素的内边距**，**`padding`** 区域指一个**元素的内容**和**其边界之间的空间**，该属性**不能为负值**。

**`padding`** 简写属性可以避免分别设置每个边的内边距，这是四个内边距属性设置的简写。四个内边距属性设置分别是: **`padding-top`**，
**`padding-right`**, **`padding-bottom`** 和 **`padding-left`**。

## 属性值

接受1~4个可选参数，每个参数取值如下：

- **只有一个** 值时，这个值会被指定给全部的 **四个边**.
- **两个** 值时，第一个值被匹配给 **上和下**, 第二个值被匹配给 **左和右**.
- **三个** 值时，第一个值被匹配给 **上**, 第二个值被匹配给 **左和右**, 第三个值被匹配给 **下**.
- **四个** 值时，会依次按 **上、右、下、左** 的顺序匹配 (即顺时针顺序).

| 属性值 | 说明 |
| :--- | :--- |
| length | 规定以具体单位计的填充值，比如**像素**、**厘米**等。默认值是 `0` |
| **`%`** | 规定基于父元素的宽度的百分比的填充 |

## CSS 属性: `padding-top`

CSS属性 **`padding-top`** 是指一个元素在内边距区域中**上方的高度**

## CSS 属性: `padding-right`

CSS属性 **`padding-right`** 是指一个元素在内边距区域中**右边的宽度**。

## CSS 属性: `padding-bottom`

CSS属性 **`padding-bottom`** 是指一个元素在内边距区域中**下方的高度**。

## CSS 属性: `padding-left`

CSS属性 **`padding-left`** 是指一个元素在内边距区域中**左边的宽度**。

## 示例

```html
<h4>This element has moderate padding.</h4>
<h3>The padding is huge in this element!</h3>
```

```css
h4 {
  background-color: lime;
  padding: 20px 50px;
}

h3 {
  background-color: cyan;
  padding: 110px 50px 50px 110px;
}
```

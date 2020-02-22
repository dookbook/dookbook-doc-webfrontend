TOPICS: text-align property
AUTHORS: Sebastian Zartner; SebastianZ@github.com; github:SebastianZ
         Dong WEI; FredWe@mozilla.net; mdn:FredWe
         庄引; zhuangyin8@gmail.com; github:zhuangyin8
         Guillaume Heras; Guillaume-Heras@mozilla.net; mdn:Guillaume-Heras
         Florian Scholz; fscholz@mozilla.net; mdn:fscholz
         Fan Sai Kuok; fskuok@mozilla.net; mdn:fskuok
         紫云飞; ziyunfei@mozilla.net; mdn:ziyunfei

# CSS 属性: `text-align`

`text-align` CSS属性定义行内内容（例如文字）如何相对它的块父元素对齐。`text-align` 并不控制块元素自己的对齐，只控制它的行内内容的对齐。

## 属性值

| 属性值 | 描述 |
| :--- | :--- |
| `left` | 把文本排列到左边。默认值：由浏览器决定。|
| `right` | 把文本排列到右边。|
| `center` | 把文本排列到中间。|
| `justify` | 实现两端对齐文本效果。|

## 示例

```css
.example {
  text-align: left;
  border: solid;
}
```

```html
<p class="example">
  Integer elementum massa at nulla placerat varius.
  Suspendisse in libero risus, in interdum massa.
  Vestibulum ac leo vitae metus faucibus gravida ac in neque.
  Nullam est eros, suscipit sed dictum quis, accumsan a ligula.
</p>
```

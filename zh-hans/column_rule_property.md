TOPICS: column-rule property
        column-rule-width property
        column-rule-style property
        column-rule-color property

# CSS 列之间直线属性: `column-rule`

在多列布局中，**`column-rule`** 属性规定了**列与列之间的直线**，也称“规则”。是 **column-rule-width**，**column-rule-style** 和 **column-rule-color**的简写属性。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **column-rule-width** | 设置多列布局中各列之间绘制的**线条的宽度**，属性值可通过 [*`border-width`*](/zh-hans/webfrontend/border-width_property) 的属性值来设置。 |
| **column-rule-style** | 设置多列布局中各列之间绘制的**线条的样式**，属性值可通过 [*`border-style`*](/zh-hans/webfrontend/border-style_property) 的属性值来设置。 |
| **column-rule-color** | 设置多列布局中各列之间绘制的**线条的颜色**，属性值可通过 [*CSS 颜色*](/zh-hans/webfrontend/css_color) 来设置。 |

## 示例

```css
.newspaper {
  column-count: 3; /* 将列分为3列 */
  column-gap: 40px; /* 列于列之间间距分为40px */
  column-rule: 4px outset #f00; /* 列于列之间的线条为4px、颜色为红色的实线 */
}
```

```html
<div class="newspaper">
当我年轻的时候，我梦想改变这个世界；当我成熟以后，我发现我不能够改变这个世界，我将目光缩短了些，决定只改变我的国家；当我进入暮年以后，我发现我不能够改变我们的国家，我的最后愿望仅仅是改变一下我的家庭，但是，这也不可能。当我现在躺在床上，行将就木时，我突然意识到：如果一开始我仅仅去改变我自己，然后，我可能改变我的家庭；在家人的帮助和鼓励下，我可能为国家做一些事情；然后，谁知道呢?我甚至可能改变这个世界。
</div>
```

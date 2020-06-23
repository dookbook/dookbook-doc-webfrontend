TOPICS: unicode-bidi property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 属性: `unicode-bidi`

CSS **`unicode-bidi`** 属性和 [**`direction`**](/zh-hans/webfrontend/direction_property) 属性，决定如何处理文档中的**双书写方向文本**。比如：如果一块内容同时包含有**从左到右书写**和**从右到左书写的文本**，
那么用户代理会使用复杂的 `Unicode` 算法来决定如何显示文本。`unicode-bidi` 属性会覆盖此算法，允许开发人员控制文本嵌入。

**`unicode-bidi`** 与 [**`direction`**](/zh-hans/webfrontend/direction_property) 是仅有的两个不受
[**`all`**](/zh-hans/webfrontend/all_property) 简写影响的属性。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`normal`** | 对双向算法，此元素不提供额外的嵌入级别。对于内联元素，隐式的重新排序在元素的边界上起作用。|
| **`embed`** | 对于内联元素，该值会为双向算法打开一个额外的嵌入级别。嵌入级别的方向是由 [*`direction`*](/zh-hans/webfrontend/direction_property) 属性给出的。|
| **`bidi-override`** | 对于内联元素，该值会创建一个覆盖；对于块容器元素，该值将为不在另一个块容器元素内的内联级别的后代创建一个覆盖。这意味着在元素内部，根据 [*`direction`*](/zh-hans/webfrontend/direction_property) 属性，重新排序是严格按照顺序排列的；双向算法的隐式部分被忽略。|
| **`isolate`** | 这个关键字表示计算元素容器的方向时，不考虑这个元素的内容。因此，这个元素就从它的兄弟姐妹中分离出来了。当应用它的双向分辨算法的时候，它的容器元素将其视为一个或多个 U+FFFC Object Replacement Character，即像 `image` 一样。|
| **`isolate-override`** | 这个关键字将 **`isolate`** 关键字的隔离行为应用于周围的内容，并将 **`bidi-override`** 关键字的覆盖行为应用于内部内容。|
| **`plaintext`** | 这个关键字在计算元素方向的时候，不考虑父元素的双向状态，也不考虑 [*`direction`*](/zh-hans/webfrontend/direction_property) 属性的值。它是使用 `Unicode` 双向算法的P2和P3规则计算的。这个值允许按照 `Unicode` 双向算法显示已经格式化的数据。|

## 示例

```css
.bible-quote {
  direction: rtl;
  unicode-bidi: embed;
}
```

```html
<div class="bible-quote">
  A line of text
</div>
<div>
  Another line of text
</div>
```

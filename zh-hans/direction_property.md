TOPICS: direction property

# CSS 属性: `direction`

CSS属性 **`direction`** 用来**设置文本**、**表列水平溢出的方向**。

值得注意的是文本方向通常由文档定义 (例如: HTML的 [**`dir`**](/zh-hans/webfrontend/dir_attribute) 属性)而不是通过直接使用 `direction`
属性定义。

该属性设置可以设置块级元素文本的基本方向，也可以设置由通过 `unicode-bidi`属性创建的嵌入元素的方向。与此同时，它还可以设置文本、块级元素的默认对齐方式 ，以及表行中的单元格的流动方向。

与 HTML 中的 [`dir`](/zh-hans/webfrontend/dir_attribute) 属性不同，`direction` 属性不会从表列继承到表单元格, 因为 CSS 继承遵从文档流,
而表单元格位于行内部, 但不在列内部。

`direction` 属性和 `unicode-bidi` 属性不受 `all` 属性影响。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`ltr`** | 默认属性。可设置文本和其他元素的默认方向是**从左到右**。|
| **`rtl`** | 可设置文本和其他元素的默认方向是**从右到左**。|

## 示例

```css
div.ex1 { direction: rtl; }
```

```html
<div>一些文本。默认的书写方向。</div>
<div class="ex1">一些文本。 Right-to-left 方向。</div>
```

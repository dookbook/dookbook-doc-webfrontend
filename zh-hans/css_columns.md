TOPICS: columns property
        column-width property
        column-count property
        column-span property
        column-rule property
        column-rule-width property
        column-rule-style property
        column-rule-color property
        column-gap property
        column-fill property

# CSS 多列 (`columns`、`column-span`、`column-rule`、`column-gap`、`column-fill`)

CSS 多列属性可以将文本内容设计成像报纸一样的多列布局

| 属性 | 说明 |
| :--- | :--- |
| **`columns`** | 用来设置元素的**列宽**和**列数**，是 **`column-width`** 和 **`column-count`** 的简写属性 |
| **`column-span`** | 当值被设置为`all`时，可以让一个元素跨越所有的列。一个跨越多列的元素被称为 **跨越元素** |
| **`column-rule`** | 设置多列布局中**各列之间**绘制的**线条的宽度**，**样式**和**颜色**，是 **`column-rule-width`**、**`column-rule-style`**和 **`column-rule-color`** 的简写属性 |
| **`column-gap`** | 设置元素的列之间的**间距的大小** |
| **`column-fill`** | 控制将元素分成几列时如何**平衡元素的内容**。 |

## CSS `column-width` 属性

CSS属性 **`column-width`** 建议一个**最佳列宽**。列宽是在添加另一列之前列将成为最大宽度。

| 属性值 | 说明 |
| :--- | :--- |
| **`auto`** | 浏览器将决定列的宽度 |
| **length** | 指定列宽的长度 |

## CSS `column-count` 属性

CSS属性 **`column-count`** 描述元素的**列数**。

| 属性值 | 说明 |
| :--- | :--- |
| **number** | 列的最佳数目将其中的元素的内容无法流出 |
| **`auto`** | 列数将取决于其他属性，例如：*`column-width`* |

## CSS `column-span` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`none`** | 元素不跨多个列 |
| **`all`** | 元素横跨所有列。元素出现之前，出现在元素之前的正常流中的内容在所有列之间自动平衡。该元素建立一个新的块格式上下文 |

## CSS `column-rule` 拆分属性

| 属性 | 说明 |
| :--- | :--- |
| **`column-rule-width`** | 设置多列布局中各列之间绘制的**线条的宽度**，属性值可通过 [*`border-width`*](/zh-hans/webfrontend/border-width_property) 的属性值来设置 |
| **`column-rule-style`** | 设置多列布局中各列之间绘制的**线条的样式**，属性值可通过 [*`border-style`*](/zh-hans/webfrontend/border-style_property) 的属性值来设置 |
| **`column-rule-color`** | 设置多列布局中各列之间绘制的**线条的颜色**，属性值可通过 [*CSS 颜色*](/zh-hans/webfrontend/css_color) 来设置 |

## CSS `column-gap` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`normal`** | 浏览器的默认间距用于各列之间。对于多列布局，将其指定为`1em`。对于所有其他布局类型，该值为`0` |
| **length** | 列之间的**间隙大小**，值必须为**正数** |

## CSS `column-fill` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`auto`** | 列按顺序填充。内容仅占用其所需的空间，这可能导致某些列保持空白 |
| **`balance`** | 内容在各列之间平均分配。在片段化的上下文中（例如分页的媒体），只有最后一个片段是平衡的。因此，在分页媒体中，只有最后一页是平衡的 |
| **`balance-all`** | 内容在各列之间平均分配。在碎片环境中，例如分页媒体，所有碎片都是平衡的。 |

## 示例

```css
.content-box {
  columns: 3 auto; /* 将把段落设为3列 */
  column-rule: solid 2px; /* 列之间设置一根2px的实线 */
  column-gap: 20px; /* 列间距为20px */
}
```

```html
<p class="content-box">
  This is a bunch of text split into three columns
  using the CSS `columns` property. The text
  is equally distributed over the columns.
</p>
```

### 使用 `column-span` 属性

```css
article {
  columns: 3;
}

h2 {
  column-span: all;
}
```

```html
<article>
  <h2>Header spanning all of the columns</h2>
  <p>
     The h2 should span all the columns. The rest
     of the text should be distributed among the columns.
  </p>
  <p>This is a bunch of text split into three columns using the CSS `columns` property. The text is equally distributed over the columns.</p>
  <p>This is a bunch of text split into three columns using the CSS `columns` property. The text is equally distributed over the columns.</p>
  <p>This is a bunch of text split into three columns using the CSS `columns` property. The text is equally distributed over the columns.</p>
  <p>This is a bunch of text split into three columns using the CSS `columns` property. The text is equally distributed over the columns.</p>
</article>
```

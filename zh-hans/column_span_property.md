TOPICS: column-span property

# CSS 属性: `column-span`

CSS **`column-span`** 属性指定某个元素应该**跨越多少列**。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`none`** | 元素**不跨多个列**。 |
| **`all`** | 元素**横跨所有列**。元素出现之前，出现在元素之前的正常流中的内容在所有列之间自动平衡。该元素建立一个新的块格式上下文。 |

## 示例

```css
article {
  columns: 3; /* 列分为3列 */
}

h2 {
  column-span: all; /* 横跨所有列 */
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

TOPICS: text-align-last property

# CSS 属性: `text-align-last`

CSS 属性 **`text-align-last`** 描述的是一段文本中最后一行在被强制换行之前的对齐规则。

## 属性值

| 属性值 | 描述 |
| :--- | :--- |
| `left` | 最后一行向左对齐。|
| `right` | 最后一行向右对齐。|
| `center` | 最后一行居中对齐。|
| `auto` | 默认值。最后一行被调整，并向左对齐。|
| `justify` | 最后一行被调整为两端对齐。|
| `start` | 最后一行在行开头对齐（如果 `text-direction` 是从左到右，则向左对齐；如果 `text-direction` 是从右到左，则向右对齐）。|
| `end` | 最后一行在行末尾对齐（如果 `text-direction` 是从左到右，则向右对齐；如果 `text-direction` 是从右到左，则向左对齐）。|

## 示例

```css
div {
  text-align: justify;
  text-align-last: right;
  -moz-text-align-last: right; /* 针对 Firefox 的代码 */
}
```

```html
<div>
You can use the text-align-last property to align the last line of a text, if the text has the text-align property set to justify. This text is where you will see the result of the  text-align-last property. You can use the text-align-last property to align the last line of a text, if the text has the text-align property set to justify. This text is where you will see the result of the  text-align-last property.
You can use the text-align-last property to align the last line of a text, if the text has the text-align property set to justify. This text is where you will see the result of the  text-align-last property.
You can use the text-align-last property to align the last line of a text, if the text has the text-align property set to justify. This text is where you will see the result of the  text-align-last property.
You can use the text-align-last property to align the last line of a text, if the text has the text-align property set to justify. This text is where you will see the result of the  text-align-last property.
You can use the text-align-last property to align the last line of a text, if the text has the text-align property set to justify. This text is where you will see the result of the  text-align-last property.
You can use the text-align-last property to align the last line of a text, if the text has the text-align property set to justify. This text is where you will see the result of the  text-align-last property.
You can use the text-align-last property to align the last line of a text, if the text has the text-align property set to justify. This text is where you will see the result of the  text-align-last property.
</div>
```

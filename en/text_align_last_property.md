TOPICS: text-align-last property

# CSS Property: `text-align-last`

The **`text-align-last`** CSS property sets how the last line of a block or a line, right before a
forced line break, is aligned.

## Property Value

| Property Value | Description |
| :--- | :--- |
| **`left`** | The inline contents are aligned to the left edge of the line box. |
| **`right`** | The inline contents are aligned to the right edge of the line box. |
| **`center`** | The inline contents are centered within the line box. |
| **`auto`** | The affected line is aligned per the value of text-align, unless text-align is justify, in which case the effect is the same as setting text-align-last to start. |
| **`justify`** | The text is justified. Text should line up their left and right edges to the left and right content edges of the paragraph. |
| **`start`** | The same as left if direction is left-to-right and right if direction is right-to-left. |
| **`end`** | The same as right if direction is left-to-right and left if direction is right-to-left. |

## Examples

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

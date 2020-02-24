TOPICS: text-align property
        text-align-last property

# CSS Property: `text-align`、`text-align-last`

The **`text-align`** CSS property sets the **horizontal alignment** of a block element or table-cell
box. This means it works like [*`vertical-align`*](/en/webfrontend/vertical-align_property) but in the
horizontal direction.

The **`text-align-last`** CSS property sets how the last line of a block or a line, right before a
forced line break, is aligned.

## `text-align` property Value

| Property Value | Description |
| :--- | :--- |
| **`left`** | The inline contents are aligned to **the left edge of the line box**. |
| **`right`** | The inline contents are aligned to **the right edge of the line box**. |
| **`center`** | The inline contents are **centered within the line box**. |
| **`justify`** | The inline contents are **justified**. Text should be spaced to line up its left and right edges to the left and right edges of the line box, except for the last line. |

## `text-align-last` property Value

| Property Value | Description |
| :--- | :--- |
| **`left`** | The inline contents are aligned to **the left edge of the line box**. |
| **`right`** | The inline contents are aligned to **the right edge of the line box**. |
| **`center`** | The inline contents are **centered within the line box**. |
| **`auto`** | The affected line is aligned per the value of text-align, unless text-align is justify, in which case the effect is the same as setting text-align-last to start. |
| **`justify`** | The text is **justified**. Text should line up their left and right edges to the left and right content edges of the paragraph. |
| **`start`** | The same as left if direction is left-to-right and right if direction is right-to-left. |
| **`end`** | The same as right if direction is left-to-right and left if direction is right-to-left. |

## Example: `text-align`

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

## Example: `text-align-last`

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

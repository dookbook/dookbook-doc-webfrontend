TOPICS: text-decoration property

# CSS Property: `text-decoration`

**`text-decoration`** CSS properties are used to set
**text layout (underline, topline, strikethrough, or blinking)**

Text decorations are drawn across descendant text elements. This means that if an element specifies
a text decoration, then a child element can't remove the decoration. For example, in the markup
`<p>This text has <em>some emphasized words</em> in it.</p>`, the style rule
`p { text-decoration: underline; }` would cause the entire paragraph to be underlined. The style
rule `em { text-decoration: none; }` would not cause any change; the entire paragraph would still
be underlined. However, the rule `em { text-decoration: overline; }` would cause a second decoration
to appear on "some emphasized words".

## Property Value

| Property Value | Description |
| :--- | :--- |
| **`none`** | Default. Standard text. |
| **`underline`** | A line under the text. |
| **`overline`** | A line on the text. |
| **`line-through`** | Cross a line under the text. |

## Examples

```css
h1 {text-decoration: overline;}
h2 {text-decoration: line-through;}
h3 {text-decoration: underline;}
```

```html
<h1>This is heading 1</h1>
<h2>This is heading 2</h2>
<h3>This is heading 3</h3>
```

TOPICS: direction property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Property: `direction`

The **`direction`** CSS property sets the direction of text, table columns, and horizontal
overflow. Use `rtl` for languages written from right to left (like Hebrew or Arabic), and `ltr` for
those written from left to right (like English and most other languages).

Note that text direction is usually defined within a document (e.g., `with` HTML's `dir` attribute)
rather than through direct use of the `direction` property.

The property sets the base text direction of block-level elements and the direction of embeddings
created by the `unicode-bidi` property. It also sets the default alignment of text, block-level
elements, and the direction that cells flow within a table row.

Unlike the `dir` attribute in HTML, the `direction` property is not inherited from table columns into
table cells, since CSS inheritance follows the document tree, and table cells are inside of rows
but not inside of columns.

The `direction` and `unicode-bidi` properties are the two only properties which are not affected by
the `all` shorthand property.

## Attribute Value

| Attribute Value | Description |
| :--- | :--- |
| `ltr` | Text and other elements go from left to right. This is the default value. |
| `rtl` | Text and other elements go from right to left. |

## Examples

```css
div.ex1 { direction: rtl; }
```

```html
<div>Some text. The default writing direction.</div>
<div class="ex1">Some text. Right-to-left direction.</div>
```

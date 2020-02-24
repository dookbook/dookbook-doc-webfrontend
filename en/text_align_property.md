TOPICS: text-align property

# CSS Property: `text-align`

The **`text-align`** CSS property sets the horizontal alignment of a block element or table-cell box.
This means it works like [`vertical-align`](/en/webfrontend/vertical-align_property) but in the
horizontal direction.

## Property Value

| Property Value | Description |
| :--- | :--- |
| `left` | The inline contents are aligned to the left edge of the line box. |
| `right` | The inline contents are aligned to the right edge of the line box. |
| `center` | The inline contents are centered within the line box. |
| `justify` | The inline contents are justified. Text should be spaced to line up its left and right edges to the left and right edges of the line box, except for the last line. |

## Examples

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

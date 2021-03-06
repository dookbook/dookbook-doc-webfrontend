TOPICS: <bdo>

# HTML Bidirectional Overlay Element: `<bdo>`

**HTML `<bdo>` bidirectional overlay element** is used to cover the current text orientation,
which causes the characters to line up in a given direction.

!!! warn "Note"
    The text's characters are drawn from the starting point in the given direction; the individual
    characters' orientation is not affected (so characters don't get drawn backward, for example).

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*, *palpable content*. |
| **Permitted content** | *Phrasing content*. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *phrasing content*. |
| **Permitted ARIA roles** | Any |
| **DOM interface** | **`HTMLElement`** Up to Gecko 1.9.2 (Firefox 4) inclusive, Firefox implements the `HTMLSpanElement` interface for this element. |

## Attributes

This element's attributes include the [global attributes](/en/webfrontend/HTML_Global_Attributes).

## Examples

```html
<!-- Switch text direction -->
<p>This text will go left to right.</p>
<p><bdo dir="rtl">This text will go right
to left.</bdo></p>
```

## Notes

The HTML 4 specification did not specify events for this element; they were added in XHTML.
This is most likely an oversight.

## Browser compatibility

| - | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
| `<bdo>`  | support | support | support |

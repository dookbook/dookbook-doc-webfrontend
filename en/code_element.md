TOPICS: <code>

# HTML `<code>`

The **HTML `<code>` element** displays its contents styled in a fashion intended to indicate that
the text is a **short fragment of computer code**. By default, the content text is displayed using the
user agent's default *monospace* font.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*, *palpable content*. |
| **Permitted content** | *Phrasing content*. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *phrasing content*. |
| **Permitted ARIA roles** | Any |
| **DOM interface** | **`HTMLElement`** |

## Attributes

This element only includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

## Example

A paragraph of text that includes `<code>`:

```html
<p>The function <code>selectAll()</code> highlights all the text in the
input field so the user can, for example, copy or delete the text.</p>
```

## Notes

To represent multiple lines of code, wrap the `<code>` element within a **[`<pre>`](/en/webfrontend/<pre>)**
element. The `<code>` element by itself only represents a *single phrase of code* or *line of code*.

A [[CSS]] rule can be defined for the code selector to override the browser's default font face.
Preferences set by the user might take precedence over the specified CSS.

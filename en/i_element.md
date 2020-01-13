TOPICS: <i>

# HTML Element: `<i>`

The **HTML `<i>` element** represents a range of text that is set off from the normal text for some
reason. Some examples include *technical terms*, *foreign language phrases*, or
*fictional character thoughts*.
It is typically displayed in *italic* type.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*, *palpable content*.|
| **Permitted content** | *Phrasing content*.|
| **Tag omission** | None, both the starting and ending tag are mandatory.|
| **Permitted parents** | Any element that accepts *phrasing content*.|
| **Permitted ARIA roles** | Any |
| **DOM Interface** | **`HTMLElement`** |

## Attributes

This element only includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

## Usage Notes

- Use the `<i>` element for text that is set off from the normal prose for readability reasons.
This would be a range of text with different semantic meaning than the surrounding text.
- In earlier versions of the HTML specification, the `<i>` element was merely a presentational
element used to display text in italics, much like the [`<b>`](/en/webfrontend/<b>) element was
used to display text in bold letters. This is no longer true, as these TOPICS now define semantics
rather than typographic appearance. A browser will typically still display the contents of the `<i>`
element in italic type, but is, by definition, no longer required to.
- Typically this element is displayed in italic type. However, it should not be used simply to apply
italic styling; use the CSS `font-style` property for that purpose.
- Be sure the text in question is not actually more appropriate for another element.
    - Use [`<em>`](/en/webfrontend/<em>) to indicate stress emphasis.
    - Use [`<strong>`](/en/webfrontend/<strong>) to indicate stronger importance.
    - Use [`<mark>`](/en/webfrontend/<mark>) to indicate relevance.
    - Use [`<cite>`](/en/webfrontend/<cite>) to mark the name of a work, such as a book, play, or song.
    - Use [`<dfn>`](/en/webfrontend/<dfn>) to mark the defining instance of a term.
- It is a good idea to use the *`class`* attribute to identify why the element is being used,
so that if the presentation needs to change at a later date, it can be done selectively with style sheets.

## Example

This example demonstrates using the `<i>` element to mark text that is in another language.

```html
<p>The Latin phrase <i class="latin">Veni, vidi, vici</i> is often
mentioned in music, art, and literature.</p>
```

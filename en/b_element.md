TOPICS: <b>
        HTMLElement

# HTML Bring Attention To Element: `<b>`

The **HTML Bring Attention To Element** (**`<b>`**) is used to **draw the reader's attention to the
element's contents**, which are not otherwise granted special importance. This was formerly known as
the *Boldface* element, and most browsers still draw the text in boldface. However, you should not use
`<b>` for styling text; instead, you should use the CSS `font-weight` property to create
boldface text, or the [`<strong>`](/en/webfrontend/<strong>) element to indicate that text is of
special importance.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content Categories** | *Flow Content*, *Phrasing Content*, *Palpable Content*. |
| **Permitted content** | *Phrasing content*. |
| **Tag omission** | None, both the starting and ending tag are mandatory.|
| **Permitted parents** | Any element that accepts *phrasing content*. |
| **Permitted ARIA roles** | Any |
| **DOM interface** | **`HTMLElement`** |

## Attributes

This element only includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

## Usage Notes

- Use the `<b>` for cases like keywords in a summary, product names in a review, or other spans of
text whose typical presentation would be boldfaced (but not including any special importance).
- Do not confuse the `<b>` element with the [`<strong>`](/en/webfrontend/<strong>), [`<em>`](/en/webfrontend/<em>),
or [`<mark>`](/en/webfrontend/<mark>) elements. The [`<strong>`](/en/webfrontend/<strong>) element
represents text of certain importance, [`<em>`](/en/webfrontend/<em>) puts some emphasis on the
text and the [`<mark>`](/en/webfrontend/<mark>) element represents text of certain relevance.
The `<b>` element doesn't convey such special semantic information; use it only when no others fit.
- Similarly, do not mark titles and headings using the `<b>` element. For this purpose, use the
[`<h1>`](/en/webfrontend/<h1>) to [`<h6>`](/en/webfrontend/<h6>) elements.
Further, stylesheets can change the default style of these elements, with the result that they are
not necessarily displayed in bold.
- It is a good practice to use the class attribute on the `<b>` element in order to convey
additional semantic information as needed (for example `<b class="lead">`
for the first sentence in a paragraph). This makes it easier to manage multiple use cases of `<b>`
if your stylistic needs change, without the need to change all of its uses in the HTML.
- Historically, the `<b>` element was meant to make text boldface. Styling information has been
deprecated since HTML4, so the meaning of the `<b>` element has been changed.
- If there is no semantic purpose to using the `<b>` element, you should use the CSS `font-weight`
property with the value `"bold"` instead in order to make text bold.

## Examples

```html
<p>
  This article describes several <b class="keywords">text-level</b> elements.
  It explains their usage in an <b class="keywords">HTML</b> document.
</p>
Keywords are displayed with the default style of the <b>
element, likely in bold.
```

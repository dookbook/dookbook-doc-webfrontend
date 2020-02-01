TOPICS: <aside>

# HTML Sidebar Element: `<aside>`

The **HTML `<aside>` element** represents a portion of a document whose content is only indirectly
related to the document's main content. Asides are frequently presented as **sidebars** or
**call-out boxes**.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *sectioning content*, *palpable content*. |
| **Permitted content** | *Flow content*. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *flow content*. Note that an `<aside>` element must not be a descendant of an [`<address>`](/en/webfrontend/<address>) element. |
| **Permitted ARIA roles** | [`feed`](https://w3c.github.io/aria/#feed), [`note`](https://w3c.github.io/aria/#note), [`presentation`](https://w3c.github.io/aria/#presentation), [`region`](https://w3c.github.io/aria/#region), [`search`](https://w3c.github.io/aria/#search)|
| **DOM interface** | **`HTMLElement`** |

## Attributes

This element only includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

## Usage Notes

- Do not use the `<aside>` element to tag parenthesized text, as this
kind of text is considered part of the main flow.

## Examples

### Using `<aside>`

This example uses `<aside>` to mark up a paragraph in an article. The paragraph is only indirectly
related to the main article content:

```html
<article>
  <p>
    The Disney movie <cite>The Little Mermaid</cite> was
    first released to theatres in 1989.
  </p>
  <aside>
    <p>
      The movie earned $87 million during its initial release.
    </p>
  </aside>
  <p>
    More info about the movie...
  </p>
</article>
```

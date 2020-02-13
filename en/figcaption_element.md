TOPICS: <figcaption>
        <figure>

# `<figcaption>`

The **HTML `<figcaption>` or Figure Caption element** represents a caption or legend describing the
rest of the contents of its parent `<figure>` element.

|  |  |
| :-- | :-- |
| **Content categories** | None. |
| **Permitted content** | *`Flow content`*. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | A `<figure>` element; the `<figcaption>` element must be its first or last child. |
| **Permitted ARIA roles** | `group`, `presentation` |
| **DOM interface** | **`HTMLElement`** |

## Attributes

This element only includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

## `<figure>`

The HTML `<figure>` (Figure With Optional Caption) element represents self-contained content,
potentially with an optional caption, which is specified using the (`<figcaption>`) element. The figure,
its caption, and its contents are referenced as a single unit.

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *sectioning root*, *palpable content*. |
| **Permitted content** | A `<figcaption>` element, followed by *flow content*; or *flow content* followed by a `<figcaption>` element; or *flow content*. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *Flow content*. |
| **Permitted ARIA roles** | `group`, `presentation` |
| **DOM interface** | **`HTMLElement`** |

## Usage Notes

- Usually a `<figure>` is an image, illustration, diagram, code snippet, etc., that is referenced
in the main flow of a document, but that can be moved to another part of the document or to an
appendix without affecting the main flow.
- Being a sectioning root, the outline of the content of the `<figure>` element is excluded
from the main outline of the document.
- A caption can be associated with the `<figure>` element by inserting a `<figcaption>` inside it
(as the first or the last child). The first `<figcaption>` element found
in the figure is presented as the figure's caption.

## Examples

### Images

```html
<!-- Just an image -->
<figure>
  <img
  src="https://developer.mozilla.org/static/img/favicon144.png"
  alt="The beautiful MDN logo.">
</figure>

<!-- Image with a caption -->
<figure>
  <img
  src="https://developer.mozilla.org/static/img/favicon144.png"
  alt="The beautiful MDN logo.">
  <figcaption>MDN Logo</figcaption>
</figure>
```

### Code snippets

```html
<figure>
  <figcaption>Get browser details using <code>navigator</code>.</figcaption>
  <pre>
function NavigatorExample() {
  var txt;
  txt = "Browser CodeName: " + navigator.appCodeName + "; ";
  txt+= "Browser Name: " + navigator.appName + "; ";
  txt+= "Browser Version: " + navigator.appVersion  + "; ";
  txt+= "Cookies Enabled: " + navigator.cookieEnabled  + "; ";
  txt+= "Platform: " + navigator.platform  + "; ";
  txt+= "User-agent header: " + navigator.userAgent  + "; ";
  console.log("NavigatorExample", txt);
}
  </pre>
</figure>
```

### Quotations

```html
<figure>
  <figcaption><cite>Edsger Dijkstra:</cite></figcaption>
  <blockquote>If debugging is the process of removing software bugs,
  then programming must be the process of putting them in.</blockquote>
</figure>
```

### Poems

```html
<figure>
  <p style="white-space:pre;">
Bid me discourse, I will enchant thine ear,
  Or like a fairy trip upon the green,
Or, like a nymph, with long dishevell'd hair,
  Dance on the sands, and yet no footing seen:
Love is a spirit all compact of fire,
  Not gross to sink, but light, and will aspire.</p>
  <figcaption><cite>Venus and Adonis</cite>,
    by William Shakespeare</figcaption>
</figure>
```

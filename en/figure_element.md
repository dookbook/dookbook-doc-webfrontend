TOPICS: <figure>
        <figcaption>

# HTML Figure Element: `<figure>` / `<figcaption>`

The **HTML `<figure>` element** represents self-contained content, potentially with an optional caption,
which is specified using the (`<figcaption>`) element. The figure, its caption, and its contents are
referenced as a single unit.

The **HTML `<figcaption>` element** is the caption/title of the image associated with it, and is
used to describe other data in its parent node `<figure>` element. This means that `<figcaption>`
must be the first or last in the `<figure>` block. At the same time, the HTML `<figcaption>` element
is optional; without this element, the picture of this parent node will just have no caption/caption.

## Technical Summary

| - | `<figure>` | `<figcaption>` |
| :-- | :-- | :-- |
| **Content categories** | *Flow content*, *sectioning root*, *palpable content*. | None. |
| **Permitted content** | A `<figcaption>` element, followed by *flow content*; or *flow content* followed by a `<figcaption>` element; or *flow content*. | *Flow content*. |
| **Tag omission** | None, both the starting and ending tag are mandatory. | None |
| **Permitted parents** | Any element that accepts **Flow content**. | A `<figure>` element; the `<figcaption>` element must be its first or last child. |
| **Permitted ARIA roles** | **`group`**, **`presentation`** | **`group`**, **`presentation`** |
| **DOM interface** | **`HTMLElement`** | **`HTMLElement`** |

## Attributes

This element only includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

## Usage Notes

- Usually a `<figure>` is an image、illustration、diagram、code snippet, etc., that is referenced
in the main flow of a document, but that can be moved to another part of the document or to an
appendix without affecting the main flow.
- Being a sectioning root, the outline of the content of the `<figure>` element is excluded
from the main outline of the document.
- A caption can be associated with the `<figure>` element by inserting a `<figcaption>` inside it
(as the first or the last child). The first `<figcaption>` element found
in the figure is presented as the figure's caption.

## Example: Images

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

## Example: Code snippets

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

## Example: Quotations

```html
<figure>
  <figcaption><cite>Edsger Dijkstra:</cite></figcaption>
  <blockquote>If debugging is the process of removing software bugs,
  then programming must be the process of putting them in.</blockquote>
</figure>
```

## Example: Poems

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

## Browser compatibility

| - | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
| `<figure>` | support | support | support |
| `<figcaption>` | support | support | support |

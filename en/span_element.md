TOPICS: <span>

# HTML Generic Inline Container: `<span>`

The **HTML `<span>` element** is a **generic inline container** for *phrasing content*, which does not
inherently represent anything. It can be used to group elements for styling purposes (using the
`class` or `id` attributes), or because they share attribute values, such as `lang`.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*.|
| **Permitted content** | *Phrasing content*.|
| **Tag omission** | None, both the starting and ending tag are mandatory.|
| **Permitted parents** | Any element that accepts *phrasing content*, or any element that accepts *flow content*.|
| **Permitted ARIA roles** | Any |
| **DOM interface** | **`HTMLSpanElement`** (before HTML5, the interface was **`HTMLElement`**) |

## Attributes

This element only includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

## Usage Notes

It should be
used only when no other semantic element is appropriate. `<span>` is very much like a *[`<div>`](/en/webfrontend/<div>)*
element, but [`<div>`](/en/webfrontend/<div>) is a block-level element whereas a `<span>`
is an inline element.Generally,[`<div>`](/zh-hans/webfrontend/<div>) is used for large layout frames,
and `<span>` is used for small parts or places where small retouching is required.

## Examples

### Simple `<span>`

```html
<p><span>Some text</span></p>
```

### Styled `<span>`

```html
<li><span>
  <a href="portfolio.html" target="_blank">See my portfolio</a>
</span></li>
```

```css
li span {
  background: gold;
}
```

## Browser compatibility

| - | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
| `<span>`| support | support | support |

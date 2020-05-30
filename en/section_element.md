TOPICS: <section>

# HTML Section Element: `<section>`

The **HTML `<section>` element** represents a **standalone section** — which doesn't have a more specific
semantic element to represent it — contained within an HTML document. Typically, but not always,
sections have a heading.

As an example, a navigation menu should be wrapped in a *[`<nav>`](/en/webfrontend/<nav>)* element,
but a list of search results and a map display and its controls don't have specific elements,
and could be put inside a `<section>`.

!!! warn "Note"
    If the contents of the element would make sense syndicated as a standalone piece, the
    *[`<article>`](/en/webfrontend/<article>/)* element may be a better choice.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *Sectioning content*, *palpable content*. |
| **Permitted content** | *Flow content*. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *flow content*. Note that a `<section>` element **must not** be a descendant of an *[`<address>`](/en/webfrontend/<address>)* element. |
| **Permitted ARIA roles** | `alert`, `alertdialog`, `application`, `banner`, `complementary`, `contentinfo`, `dialog`, `document`, `feed`, `log`, `main`, `marquee`, `navigation`, `search`, `status`, `tabpanel` |
| **DOM interface** | **`HTMLElement`** |

## Attributes

This element only includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

## Usage Notes

- Each `<section>` should be identified, typically by including a heading
(*[`<h1>`](/en/webfrontend/<h1>)* - *[`<h6>`](/en/webfrontend/<h6>)* element)
as a child of the `<section>` element.
- If it makes sense to separately syndicate the content of a `<section>` element,
use an *[`<article>`](/en/webfrontend/<article>)* element instead.
- Do not use the `<section>` element as a generic container; this is what
*[`<div>`](/en/webfrontend/<div>)* is for,
especially when the sectioning is only for styling purposes. A rule of thumb is that a `<section>` should
logically appear in the outline of a document.

## Example

Before

```html
<div>
  <h1>Heading 1</h1>
  <p>Bunch of awesome content</p>
</div>

<div>
  <h2>Heading 2</h2>
  <img src="bird.jpg" alt="bird">
</div>
```

After

```html
<article>
  <section>
    <h1>Heading 1</h1>
    <p>Bunch of awesome content</p>
  </section>

  <section>
    <h2>Heading 2</h2>
    <img src="bird.jpg" alt="bird">
  </section>
</article>
```

## Browser compatibility

| - | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
| `<section>` | support | support | support |

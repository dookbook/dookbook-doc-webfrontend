TOPICS: <hgroup>

# `<hgroup>`

The **HTML `<hgroup>` element** represents a multi-level heading for a section of a document.
It groups a set of [`<h1>`](/en/webfrontend/<h1>)–[`<h6>`](/en/webfrontend/<h6>) elements.

|  |  |
| :-- | :-- |
| **Content categories** | Flow content, heading content, palpable content. |
| **Permitted content** | One or more [`<h1>`](/en/webfrontend/<h1>), [`<h2>`](/en/webfrontend/<h2>), [`<h3>`](/en/webfrontend/<h3>), [`<h4>`](/en/webfrontend/<h4>), [`<h5>`](/en/webfrontend/<h5>), and/or [`<h6>`](/en/webfrontend/<h6>). |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts flow content.|
| **Permitted ARIA roles** | `tab`, `presentation` |
| **DOM interface** | `HTMLElement` |

## Attributes

This element only includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

## Usage Notes

!!! warn "Don't try this at home"
    The `<hgroup>` element has been removed from the HTML5 (W3C) specification, but it still is in the
    WHATWG version of HTML. It is partially implemented in most browsers, though,
    so is unlikely to go away.
    However, given that a key purpose of the `<hgroup>` element is to affect how headings are displayed
    by the outline algorithm defined in
    **the HTML specification—but the HTML outline algorithm is not implemented in any browsers** —then
    the `<hgroup>` semantics are in practice only theoretical.
    So the HTML5 (W3C) specification provides advice on how to mark up
    [Subheadings, subtitles, alternative titles and taglines](https://www.w3.org/TR/html52/common-idioms-without-dedicated-elements.html#common-idioms-without-dedicated-elements)
    without using `<hgroup>`.

The `<hgroup>` element allows the primary heading for a document section to be grouped with any
secondary headings—such as subheadings or alternative titles—to form a multi-level heading.

In other words, the `<hgroup>` element prevents any of its secondary
[`<h1>`](/en/webfrontend/<h1>)–[`<h6>`](/en/webfrontend/<h6>) children
from creating separate sections of their own in the outline—as those
[`<h1>`](/en/webfrontend/<h1>)–[`<h6>`](/en/webfrontend/<h6>) elements
otherwise normally would if they were not children of any `<hgroup>`.

So in the abstract outline produced by the HTML outline algorithm defined in the HTML specification,
the `<hgroup>` as a whole forms a single logical heading, with the entire set of
[`<h1>`](/en/webfrontend/<h1>)–[`<h6>`](/en/webfrontend/<h6>) children of the
`<hgroup>` going into the outline as one multi-level unit,
to comprise that single logical heading in the abstract outline.

To produce any (non-abstract) rendered view of such an outline, some choice must be made in the
design of the rendering tool about how to render `<hgroup>` headings in such a way as to convey
their multi-level nature. There are a variety of ways an `<hgroup>`
might be shown in a rendered outline; for example:

- an `<hgroup>` might be shown in a rendered outline in with a colon character and space (“: ”) or
other such punctuation after the primary heading and before the first secondary heading (and with
the same or similar punctuation before any other secondary headings
- an `<hgroup>` might be shown in a rendered outline in with the primary heading
followed by parentheses around the secondary heading(s)

Consider the following HTML document:

```html
<!DOCTYPE html>
<title>HTML Standard</title>
<body>
  <hgroup id="document-title">
    <h1>HTML</h1>
    <h2>Living Standard — Last Updated 12 August 2016</h2>
  </hgroup>
  <p>Some intro to the document.</p>
  <h2>Table of contents</h2>
  <ol id=toc>...</ol>
  <h2>First section</h2>
  <p>Some intro to the first section.</p>
</body>
```

A rendered outline for that document might look like the following:

![outline-colon](/media/webfrontend__outline-colon.png)

That is, the rendered outline might show the primary title, HTML, followed by a colon and space,
followed by the secondary title, Living Standard — Last Updated 12 August 2016.

Or, the rendered outline for that document might instead look like the following:

![outline-paren](/media/webfrontend__outline-paren.png)

Rendered outline that includes an `<hgroup>` element, with parens around the secondary heading

That is, the rendered outline might show the primary title, HTML, followed by the secondary title
shown in parentheses: (Living Standard — Last Updated 12 August 2016).

## Examples

```html
<hgroup id="document-title">
  <h1>HTML</h1>
  <h2>Living Standard — Last Updated 12 August 2016</h2>
</hgroup>
```

## Browser compatibility

| - | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
| `<hgroup>` | support | support | support |

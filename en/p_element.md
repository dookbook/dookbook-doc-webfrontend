TOPICS: <p>

# HTML Paragraph Element: `<p>`

The **HTML `<p>` element** represents a **paragraph**. Paragraphs are usually represented in visual
media as blocks of text separated from adjacent blocks by blank lines and/or first-line indentation,
but HTML paragraphs can be any structural grouping of related content, such as images or form fields.

Paragraphs are *block-level* elements, and notably will automatically close if another
block-level element is parsed before the closing `</p>` tag. See “**Tag omission**” below.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *palpable content*. |
| **Permitted content** | *Phrasing content*. |
| **Tag omission** | The start tag is required. The end tag may be omitted if the `<p>` element is immediately followed by an [`<address>`](/en/webfrontend/<address>), [`<article>`](/en/webfrontend/<article>), [`<aside>`](/en/webfrontend/<aside>), [`<blockquote>`](/en/webfrontend/<blockquote>), [`<div>`](/en/webfrontend/<div>), [`<dl>`](/en/webfrontend/<dl>), [`<fieldset>`](/en/webfrontend/<fieldset>), [`<footer>`](/en/webfrontend/<footer>), [`<form>`](/en/webfrontend/<form>), [`<h1>`](/en/webfrontend/<h1>), [`<h2>`](/en/webfrontend/<h2>), [`<h3>`](/en/webfrontend/<h3>), [`<h4>`](/en/webfrontend/<h4>), [`<h5>`](/en/webfrontend/<h5>), [`<h6>`](/en/webfrontend/<h6>), [`<header>`](/en/webfrontend/<header>), [`<hr>`](/en/webfrontend/<hr>), [`<menu>`](/en/webfrontend/<menu>), [`<nav>`](/en/webfrontend/<nav>), [`<ol>`](/en/webfrontend/<ol>), [`<pre>`](/en/webfrontend/<pre>), [`<section>`](/en/webfrontend/<section>), [`<table>`](/en/webfrontend/<table>), [`<ul>`](/en/webfrontend/<ul>) or another `<p>` element, or if there is no more content in the parent element and the parent element is not an [`<a>`](/en/webfrontend/<a>) element. |
| **Permitted parents** | Any element that accepts *flow content*. |
| **Permitted ARIA roles** | Any |
| **DOM interface** | **`HTMLParagraphElement`** |

## Attributes

This element only includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

!!! warn "Note"
    The `align` attribute on `<p>` is obsolete and shouldn't be used.

## Example

```html
<p>This is the first paragraph of text.
  This is the first paragraph of text.
  This is the first paragraph of text.
  This is the first paragraph of text.</p>
<p>This is the second paragraph.
  This is the second paragraph.
  This is the second paragraph.
  This is the second paragraph.</p>
```

## Accessibility Concerns

Breaking up content into paragraphs helps make a page more accessible. Screen-readers and other
assistive technology provide shortcuts to let their users skip to the next or previous paragraph,
letting them skim content like how white space lets visual users skip around.

Using empty `<p>` elements to add space between paragraphs is problematic for people who navigate
with screen-reading technology. Screen readers may announce the paragraph's presence, but not any
content contained within it — because there is none. This can confuse and frustrate
the person using the screen reader.

If extra space is desired, use CSS properties like `margin` to create the effect:

```css
p {
  margin-bottom: 2em; /* increase white space after a paragraph */
}
```

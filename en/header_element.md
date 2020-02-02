TOPICS: <header>

# HTML Introductory Content Element: `<header>`

The HTML `<header>` element represents **introductory content**, typically a group of *introductory*
or *navigational* aids. It may contain some heading elements but also a logo,
a search form, an author name, and other elements.

## Technical Summary

|||
| :-- | :--|
| **Content categories** | *Flow content*, *palpable content*.|
| **Permitted content** | *Flow content*, but with no ~~`<header>`~~ or ~~[`<footer>`](/en/webfrontend/<footer>)~~ descendant.|
| **Tag omission** | None, both the starting and ending tag are mandatory.|
| **Permitted parents** | Any element that accepts *flow content*. Note that a `<header>` element must not be a descendant of an *[`<address>`](/en/webfrontend/<address>)*, *[`<footer>`](/en/webfrontend/<footer>)* or another *`<header>`* element.|
| **Permitted ARIA roles** | `group`, `presentation`|
| **DOM interface** | **`HTMLElement`** |

## Usage Notes

The `<header>` element is not *sectioning content* and therefore does not introduce a new section in
the outline. That said, a `<header>` element is intended to usually contain the surrounding
section's heading (an `<h1>`–`<h6>` element), but this is **not** required.

### Historical Usage

Although the `<header>` element didn't make its way into specifications until HTML5, it actually
existed at the very beginning of HTML. As seen in the very first website, it was originally
used as the `<head>` element. At some point, it was decided to use a different name. This allowed
`<header>` to be free to fill a different role later on.

## Attributes

This element only includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

## Examples

### Page Header

```html
<header>
  <h1>Main Page Title</h1>
  <img src="mdn-logo-sm.png" alt="MDN logo">

  <!-- include navigation -->
  <nav>
    <a href="/home/" title="Home">Home</a>
    <a href="/tab1/" title="Tab 1">Tab 1</a>
    <a href="/tab2/" title="Tab 2">Tab 2</a>
  </nav>
</header>
```

### Article Header

```html
<article>
  <header>
    <h2>The Planet Earth</h2>
    <p>Posted on Wednesday, <time datetime="2017-10-04">4 October 2017</time> by Jane Smith</p>
  </header>
  <p>We live on a planet that's blue and green, with so many things still unseen.</p>
  <p><a href="https://dookbook.info/">Continue reading....</a></p>
</article>
```

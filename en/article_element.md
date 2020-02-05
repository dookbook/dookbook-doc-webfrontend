TOPICS: <article>

# HTML Self-Contained Composition Element: `<article>`

The **HTML `<article>` element** represents a **self-contained composition** in a *document*, *page*,
*application*, or *site*, which is intended to be **independently distributable or reusable**
(e.g., in syndication). Examples include: a forum post, a magazine or newspaper article, or a blog entry.

A given document can have multiple articles in it; for example, on a blog that shows the text of
each article one after another as the reader scrolls, each post would be contained
in an `<article>` element, possibly with one or more [`<section>`](/en/webfrontend/<section>) s within.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *sectioning content*, *palpable content*. |
| **Permitted content** | *Flow content*. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts flow content. Note that an `<article>` element must not be a descendant of an *[`<address>`](/en/webfrontend/<address>)* element. |
| **Permitted ARIA roles** | [`application`](https://w3c.github.io/aria/#application), [`document`](https://w3c.github.io/aria/#document), [`feed`](https://w3c.github.io/aria/#feed), [`main`](https://w3c.github.io/aria/#main), [`presentation`](https://w3c.github.io/aria/#presentation), [`region`](https://w3c.github.io/aria/#region) |
| **DOM interface** | **`HTMLElement`** |

## Attributes

This element only includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

## Usage Notes

- Each `<article>` should be identified, typically by including a heading
([`<h1>`](/en/webfrontend/<h1>) element)-[`<h6>`](/en/webfrontend/<h6>) element) element)
as a child of the `<article>` element.
- When an `<article>` element is nested, the inner element represents an article related to the
outer element. For example, the comments of a blog post can be `<article>`
elements nested in the `<article>` representing the blog post.
- Author information of an `<article>` element can be provided through the
[`<address>`](/en/webfrontend/<address>) element) element,
but it doesn't apply to nested `<article>` elements.
- The publication date and time of an `<article>` element can be described using the datetime
attribute of a *[`<time>`](/en/webfrontend/<time>)* element) element. **Note that the `pubdate` attribute
of [`<time>`](/en/webfrontend/<time>) element)
is no longer a part of the W3C HTML5 standard**.

## Examples

```html
<article class="film_review">
  <header>
    <h2>Jurassic Park</h2>
  </header>
  <section class="main_review">
    <p>Dinos were great!</p>
  </section>
  <section class="user_reviews">
    <article class="user_review">
      <p>Way too scary for me.</p>
      <footer>
        <p>
          Posted on
          <time datetime="2015-05-16 19:00">May 16</time>
          by Lisa.
        </p>
      </footer>
    </article>
    <article class="user_review">
      <p>I agree, dinos are my favorite.</p>
      <footer>
        <p>
          Posted on
          <time datetime="2015-05-17 19:00">May 17</time>
          by Tom.
        </p>
      </footer>
    </article>
  </section>
  <footer>
    <p>
      Posted on
      <time datetime="2015-05-15 19:00">May 15</time>
      by Staff.
    </p>
  </footer>
</article>
```

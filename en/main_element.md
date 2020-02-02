TOPICS: <main>
SYNONYM: skipnav = Skip Navigation

# HTML Dominant Content Element: `<main>`

The HTML `<main>` element represents the **dominant content** of the *[`<body>`](/en/webfrontend/<body>/)*
of a document. The main content area consists of content that is directly related to or expands upon
the *central TOPICS of a document*, or the *central functionality of an application*.

A document mustn't have more than one `<main>` element that doesn't have the `hidden` attribute specified.

## Technical Summary

| | |
| :-- | :-- |
| **Content categories** | *Flow content*, *palpable content*.|
| **Permitted content** | *Flow content*. |
| **Tag omission** | None; both the starting and ending tags are mandatory.|
| **Permitted parents** | Where *flow content* is expected, but only if it is a hierarchically correct `<main>` element.|
| **Permitted ARIA roles** | The `main` role is applied to `<main>` by default, and the `presentation` role is permitted as well.|
| **DOM interface** | **`HTMLElement`** |

## Attributes

This element only includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

## Usage Notes

The content of a `<main>` element should be **unique** to the document. Content that is repeated across
a set of documents or document sections such as sidebars, navigation links, copyright information,
site logos, and search forms shouldn't be included unless the search form is
the main function of the page.

`<main>` doesn't contribute to the document's outline; that is, unlike elements such as
[`<body>`](/en/webfrontend/<body>/), headings such as [`<h2>`](/en/webfrontend/<h2>), and such,
`<main>` doesn't affect the DOM's concept of the structure of the page. It's strictly informative.

## Example

```html
<!-- other content -->

<main>
  <h1>Apples</h1>
  <p>The apple is the pomaceous fruit of the apple tree.</p>

  <article>
    <h2>Red Delicious</h2>
    <p>These bright red apples are the most common found in many
    supermarkets.</p>
    <p>... </p>
    <p>... </p>
  </article>

  <article>
    <h2>Granny Smith</h2>
    <p>These juicy, green apples make a great filling for
    apple pies.</p>
    <p>... </p>
    <p>... </p>
  </article>
</main>

<!-- other content: sidebars, navigation links, 
copyright information,
site logos, and search forms -->
```

## Accessibility Concerns

### Landmark

The `<main>` element behaves like a `main` **landmark** role. **Landmarks** can be used by
assistive technology to quickly *identify* and *navigate* to large sections of the document. Prefer
using the `<main>` element over declaring `role="main"`, unless there are legacy browser support concerns.

### Skip Navigation

**Skip navigation**, also known as "*skipnav*", is a technique that allows an assistive technology user
to **quickly bypass** large sections of repeated content (main navigation, info banners, etc.).
This lets the user access the main content of the page faster.

Adding an `id` attribute to the `<main>` element lets it be a target of a skip navigation link.

```html
<body>
  <a href="#main-content">Skip to main content</a>

  <!-- navigation and header content -->

  <main id="main-content">
    <!-- main page content -->
  </main>
</body>
```

### Reader Mode

Browser reader mode functionality looks for the presence of the `<main>` element, as well as
heading and content sectioning elements when converting content into a specialized reader view.

- [Building websites for Safari Reader Mode and other reading apps](https://medium.com/@mandy.michael/building-websites-for-safari-reader-mode-and-other-reading-apps-1562913c86c9)

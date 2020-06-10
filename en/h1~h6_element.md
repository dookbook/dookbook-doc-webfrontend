TOPICS: <h1>
        <h2>
        <h3>
        <h4>
        <h5>
        <h6>

# HTML Heading Element: `<h1>` ~ `<h6>`

The **HTML Heading elements** (**`<h1>`** ~ **`<h6>`**) represent six levels of section headings.
`<h1>` is the highest section level and `<h6>` is the lowest.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content Categories** | *Flow content*, *heading content*, *palpable content*. |
| **Permitted Content** | *Phrasing content*. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *flow content*; don't use a heading element as a child of the [`<hgroup>`](/en/webfrontend/<hgroup>) element — it is now deprecated.|
| **Permitted ARIA roles** | `tab`, `presentation` |
| **DOM Interface** | **`HTMLHeadingElement`** |

## Attributes

These elements only include the [global attributes](/en/webfrontend/HTML_Global_Attributes).

!!! warn "Obsolete"
    The `align` attribute is obsolete; don't use it.

## Usage Notes

- Heading information may be used by user agents, for example, to construct a table of contents for
a document automatically.
- Avoid using heading TOPICS to resize text. Instead, use the [[CSS]] *`font-size`* property. Headings
use size to indicate their relative importance, but [[CSS]] is preferred for general-purpose resizing.
- Avoid skipping heading levels: always start from `<h1>`, next use `<h2>` and so on.
- You should consider avoiding using `<h1>` more than once on a page. See Defining sections
for more information.

## Examples

### All headings

The following code shows all the heading levels, in use.

```html
<h1>Heading level 1</h1>
<h2>Heading level 2</h2>
<h3>Heading level 3</h3>
<h4>Heading level 4</h4>
<h5>Heading level 5</h5>
<h6>Heading level 6</h6>
```

### Example page

The following code shows a few headings with some content under them.

```html
<h1>Heading elements</h1>
<h2>Summary</h2>
<p>Some text here...</p>

<h2>Examples</h2>
<h3>Example 1</h3>
<p>Some text here...</p>

<h3>Example 2</h3>
<p>Some text here...</p>

<h2>See Also</h2>
<p>Some text here...</p>
```

## Accessibility Concerns

### Navigation

A common navigation technique for users of screen reading software is jumping from heading to heading
to quickly determine the content of the page. Because of this, it is important to not skip one or more
heading levels. Doing so may create confusion, as the person navigating this way may be
left wondering where the missing heading is.

Don't

```html
<h1>Heading level 1</h1>
<h3>Heading level 3</h3>
<h4>Heading level 4</h4>
```

Do

```html
<h1>Heading level 1</h1>
<h2>Heading level 2</h2>
<h3>Heading level 3</h3>
```

### Nesting

Headings may be nested as subsections to reflect the organization of the content of the page. Most
screen readers can also generate an ordered list of all the headings on a page, which can help a
person quickly determine the hierarchy of the content:

1. `h1` Beetles
   1. `h2` Etymology
   2. `h2` Distribution and Diversity
   3. `h2` Evolution
      1. `h3` Late Paleozoic
      2. `h3` Jurassic
      3. `h3` Cretaceous
      4. `h3` Cenozoic
   4. `h2` External Morphology
      1. `h3` Head
         1. `h4` Mouthparts
      2. `h3` Thorax
         1. `h4` Prothorax
         2. `h4` Pterothorax
      3. `h3` Legs
      4. `h3` Wings
      5. `h3` Abdomen

When headings are nested, heading levels may be "skipped" when closing a subsection.

- [Headings • Page Structure • WAI Web Accessibility Tutorials](https://www.w3.org/WAI/tutorials/page-structure/headings/)
- MDN Understanding WCAG, Guideline 1.3 explanations
    - [Understanding Success Criterion 1.3.1 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-programmatic.html)
- MDN Understanding WCAG, Guideline 2.4 explanations
    - [Understanding Success Criterion 2.4.1 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-skip.html)
    - [Understanding Success Criterion 2.4.6 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-descriptive.html)
    - [Understanding Success Criterion 2.4.10 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-headings.html)

### Labeling section content

Another common navigation technique for users of screen reading software is to generate a list of
sectioning content and use it to determine the page's layout.

Sectioning content can be labeled using a combination of the `aria-labelledby` and `id`
attributes, with the label concisely describing the purpose of the section. This technique is
useful for situations where there is more than one sectioning element on the same page.

For example:

```html
<header>
  <nav aria-labelledby="primary-navigation">
    <h2 id="primary-navigation">Primary navigation</h2>
    <!-- navigation items -->
  </nav>
</header>

<!-- page content -->

<footer>
  <nav aria-labelledby="footer-navigation">
    <h2 id="footer-navigation">Footer navigation</h2>
    <!-- navigation items -->
  </nav>
</footer>
```

In this example, screen reading technology would announce that there are two
[`<nav>`](/en/webfrontend/<nav>) sections, one called "*Primary navigation*" and one called
"*Footer navigation*". If labels were not provided, the person using screen reading software may have
to investigate each nav element's contents to determine their purpose.

- [Using the `aria-labelledby` attribute](https://wiki.developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-labelledby_attribute)
- [Labeling Regions • Page Structure • W3C WAI Web Accessibility Tutorials](https://www.w3.org/WAI/tutorials/page-structure/labels/#using-aria-labelledby)

## Browser compatibility

| - | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
| `<h1>~<h6>` | support | support | support |

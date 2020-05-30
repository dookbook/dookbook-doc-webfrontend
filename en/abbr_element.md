TOPICS: <abbr>

# HTML Abbreviation Element: `<abbr>`

The **HTML abbreviation element** (**`<abbr>`**) represents an **abbreviation** or **acronym**.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*, *palpable content* |
| **Permitted content** | *Phrasing content* |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *phrasing content* |
| **Permitted ARIA roles** | Any |
| **DOM interface** | **`HTMLElement`** |

## Attributes

This element only supports the [global attributes](/en/webfrontend/HTML_Global_Attributes).

The optional **`title`** attribute has a specific semantic
meaning when used with the `<abbr>` element; it must contain a full human-readable description or
expansion of the abbreviation and nothing else.
This text is often presented by browsers as a **tooltip** when the mouse
cursor is hovered over the element.

!!! warn "Usage Notes"
    Each `<abbr>` element you use is independent from all others; providing a `title` for one does not
    automatically attach the same expansion text to others with the same content text.

## Typical Use Cases

It's certainly not required that all abbreviations be marked up using *`<abbr>`*. There are, though,
a few cases where it's helpful to do so:

- When an abbreviation is used and you want to provide an expansion or definition outside the flow
of the document's content, use `<abbr>` with an appropriate `title`.
- To define an abbreviation which may be unfamiliar to the reader, present the term using `<abbr>`
and either a `title` attribute or inline text providing the definition.
- When an abbreviation's presence in the text needs to be semantically noted, the `<abbr>` element
is useful. This can be used, in turn, for styling or scripting purposes.
- You can use `<abbr>` in concert with *[`<dfn>`](/en/webfrontend/<dfn>)* to establish definitions
for terms which are abbreviations or acronyms. See the example Defining an abbreviation below.

## Grammar considerations

In languages with **[grammatical number](https://en.wikipedia.org/wiki/grammatical%20number)**
(that is, languages where the number of items affects
the grammar of a sentence), use the same grammatical number in your *`title`* attribute as inside your
`<abbr>` element. This is especially important in languages with more than two numbers, such as Arabic,
but is also relevant in English.

## Default Styling

The purpose of this element is purely for the convenience of the author and all browsers display it
inline (`display: inline`) by default.

## Examples

### Marking up an abbreviation semantically

To mark up an abbreviation without providing an expansion or description, simply use `<abbr>`
without any attributes, as seen in this example.

```html
<p>Using <abbr>HTML</abbr> is fun and easy!</p>
```

### Styling Abbreviations

You can use CSS to set a custom style to be used for abbreviations, as seen in this simple example.

HTML

```html
<p>Using <abbr>CSS</abbr>, you can style your abbreviations!</p>
```

CSS

```css
abbr {
  font-variant: all-small-caps;
}
```

### Providing an expansion

Adding a *`title`* attribute lets you provide an expansion or
definition for the abbreviation or acronym.

```html
<p>Ashok's joke made me <abbr title="Laugh Out Loud">LOL</abbr> big
time.</p>
```

### Defining an abbreviation

You can use `<abbr>` in tandem with [`<dfn>`](/en/webfrontend/<dfn>) to more formally define an abbreviation,
as shown here.

```html
<p><dfn id="html"><abbr title="HyperText Markup Language">HTML</abbr>
</dfn> is a markup language used to create the semantics and structure
of a web page.</p>

<p>A <dfn id="spec">Specification</dfn>
(<abbr title="Specification">spec</abbr>) is a document that outlines
in detail how a technology or API is intended to function and how it is
accessed.</p>
```

## Accessibility Concerns

Spelling out the acronym or abbreviation in full the first time it is used on a page is beneficial
for helping people understand it, especially if the content is technical or industry jargon.

Example

```html
<p>JavaScript Object Notation (<abbr>JSON</abbr>) is a lightweight data-interchange format.</p>
```

This is especially helpful for people who are unfamiliar with the terminology or concepts discussed
in the content, people who are new to the language, and people with cognitive concerns.

## Browser compatibility

| - | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
| `<abbr>` | support | support | support |

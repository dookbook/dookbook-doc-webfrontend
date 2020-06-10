TOPICS: <bdi>

# HTML Bidirectional Isolate Element: `<bdi>`

The **HTML Bidirectional Isolate element `<bdi>`** tells the browser's bidirectional algorithm to
treat the text it contains in isolation from its surrounding text. This tag is useful when you don't
know from which direction to embed text, such as text from a database (especially the text direction
of the database); for example, when posting user reviews or other content that you don't have full
control over.

!!! warn "Node"
    Although the same display effect can be **`unicode-bidi`** using CSS rules: Isolate [`<span>`](/en/webfrontend/<span>)
    or other text formatting elements, but semantic information can only be passed through the `<bdi>`
    element. In particular, when the browser allows CSS styles to be ignored, in this case, using `<bdi>`
    still guarantees that the text is displayed correctly, and using CSS styles to convey semantics
    is useless.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*, *palpable content*. |
| **Permitted content** | *Phrasing content*. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *phrasing content*. |
| **Permitted ARIA roles** | Any |
| **DOM interface** | **`HTMLElement`** |

## Attributes

This element's attributes include the [global attributes](/en/webfrontend/HTML_Global_attributes).

## Example: No `<bdi>` with only LTR

This example lists the winners of a competition using [`<span>`](/en/webfrontend/<span>) elements only.
When the names only contain LTR text the results look fine:

```html
<ul>
 <li><span class="name">Henrietta Boffin</span> - 1st place</li>
 <li><span class="name">Jerry Cruncher</span> - 2nd place</li>
</ul>
```

## Example: No `<bdi>` with RTL text

This example lists the winners of a competition using [`<span>`](/en/webfrontend/<span>) elements
only, and one of the winners has a name consisting of RTL text. In this case the "- 1", which
consists of characters with neutral or weak directionality, will adopt the directionality of the
RTL text, and the result will be garbled:

```html
<ul>
 <li><span class="name">اَلأَعْشَى</span> - 1st place</li>
 <li><span class="name">Jerry Cruncher</span> - 2nd place</li>
</ul>
```

## Example: Using `<bdi>` with LTR and RTL text

This example lists the winners of a competition using `<bdi>` elements. These elements instruct the
browser to treat the name in isolation from its embedding context,
so the example output is properly ordered:

```html
<ul>
 <li><bdi class="name">اَلأَعْشَى</bdi> - 1st place</li>
 <li><bdi class="name">Jerry Cruncher</bdi> - 2nd place</li>
</ul>
```

## Other examples

```html
<p dir="ltr">This arabic word <bdi>ARABIC_PLACEHOLDER</bdi> is automatically displayed right-to-left.</p>
```

## Browser compatibility

| - | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
| `<bdi>`  | support | support | support |

TOPICS: <bdi>
        <bdi> dir attribute

# HTML Bidirectional Isolate Element: `<bdi>`

The **HTML Bidirectional Isolate element `<bdi>`** tells the browser's bidirectional algorithm to
treat the text it contains in isolation from its surrounding text. This tag is useful when you don't
know from which direction to embed text, such as text from a database (especially the text direction
of the database); for example, when posting user reviews or other content that you don't have full
control over.

Bidirectional text is text that may contain both sequences of characters that are arranged
left-to-right (LTR) and sequences of characters that are arranged right-to-left (RTL), such as an
Arabic quotation embedded in an English string. Browsers implement the
[Unicode Bidirectional Algorithm](https://www.w3.org/International/articles/inline-bidi-markup/uba-basics)
to handle this. In this algorithm, characters are given an
implicit directionality: for example, Latin characters are treated as LTR while Arabic characters
are treated as RTL. Some other characters (such as spaces and some punctuation) are treated as
neutral and are assigned directionality based on that of their surrounding characters.

Usually, the bidirectional algorithm will do the right thing without the author having to provide
any special markup but, occasionally, the algorithm needs help.
That's where `<bdi>` comes in.

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

| Attribute Value | Description |
| :-- | :-- |
| `dir` | Like all other HTML elements, this element supports the [global attributes](/en/webfrontend/HTML_Global_Attributes),except that the`dir` attribute behaves differently than normal: it defaults to auto, meaning its value is never inherited from the parent element. This means that unless you specify a value of either `"rtl"` or `"ltr"` for `dir`, the user agent will determine the correct directionality to use based on the contents of the `<bdi>`. |

## 使用说明

The `<bdi>` element is used to wrap a span of text and instructs the bidirectional algorithm to
treat this text in isolation from its surroundings. This works are two advantages:

- The directionality of text embedded in `<bdi>` does not influence the
directionality of the surrounding text.
- The directionality of text embedded in `<bdi>` is not influenced by the directionality
of the surrounding text.

Although the `<span>` and `<bdi>` elements can achieve the same visual effects on CSS rules, the author
does not recommend this method in HTML because it does not conform to semantics and allows browsers
to ignore CSS styles.

## No `<bdi>` with only LTR

This example lists the winners of a competition using [`<span>`](/en/webfrontend/<span>) elements only.
When the names only contain LTR text the results look fine:

```html
<ul>
 <li><span class="name">Henrietta Boffin</span> - 1st place</li>
 <li><span class="name">Jerry Cruncher</span> - 2nd place</li>
</ul>
```

## No `<bdi>` with RTL text

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

## Using `<bdi>` with LTR and RTL text

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

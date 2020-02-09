TOPICS: <ruby>
        <rp>
        <rt>
        <rb>
        <rtc>

# HTML Ruby Annotation Element: `<ruby>`/`<rp>`/`<rt>`/`<rb>`

The **HTML `<ruby>` element** represents a **ruby annotation**. Ruby annotations are for showing
pronunciation of *East Asian* characters.

The **HTML Ruby Fallback Parenthesis element** (**`<rp>`**) is used to provide **fall-back**
parentheses for
browsers that do not support display of ruby annotations using the *`<ruby>`* element. One `<rp>`
element should enclose each of the opening and closing parentheses that wrap the `<rt>` element
that contains the annotation's text.

The **HTML Ruby Text element** (**`<rt>`**) specifies the **ruby text component** of a ruby annotation,
which is used to provide *pronunciation*, *translation*, or *transliteration* information for East Asian
typography. It must always be contained within a *`<ruby>`* element.

The **HTML Ruby Base element** (**`<rb>`**) is used to **delimit the base text** component of a `<ruby>`
annotation, i.e. the text that is being annotated. One `<rb>` element should wrap each separate
atomic segment of the base text.

## Technical Summary

| - | `<ruby>` | `<rp>` | `<rt>` | `<rb>` |
| :-- | :-- | :-- | :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*, *palpable content*. | None. | None. | None. |
| **Permitted content** | *Phrasing content*.| Text | *Phrasing content*. | As a child of a *`<ruby>`* element.|
| **Tag omission** | None, both the starting and ending tag are mandatory. | The end tag can be omitted if the element is immediately followed by an `<rt>` or `<rp>` element, or if there is no more content in the parent element. | The end tag may be omitted if the element is immediately followed by an `<rt>` or `<rp>` element, or if there is no more content in the parent element. | The end tag can be omitted if the element is immediately followed by an `<rt>`, `<rtc>`, or `<rp>` or `<rb>` element, or if there is no more content in the parent element.|
| **Permitted parents** | Any element that accepts *phrasing content*.| A *`<ruby>`* element. `<rp>` must be positioned immediately before or after an *`<rt>`* element. | A *`<ruby>`* element. | A *`<ruby>`* element. |
| **Permitted ARIA roles** | Any | Any | Any | Any |
| **DOM interface** | **`HTMLElement`** | **`HTMLElement`** | **`HTMLElement`** | **`HTMLElement`** |

## Attributes

This element only includes the [global attributes](/en/webfrontend/HTML_Global_Attributes)

## Basic Usage Notes

Ruby annotations are for showing pronunciation of East Asian characters, like using Japanese
furigana or Taiwanese bopomofo characters. The *`<rp>`* element is used in the case of lack of `<ruby>`
element support; the `<rp>` content provides what should be displayed in order to indicate the
presence of a ruby annotation, usually parentheses.

```html
<ruby>
  漢 <rp>(</rp><rt>Kan</rt><rp>)</rp>
  字 <rp>(</rp><rt>ji</rt><rp>)</rp>
</ruby>
```

## `<rb>` Usage Notes

- The *`<rb>`* element is used to separate out each segment
of the ruby base text.
- Even thought `<rb>` is not an empty element, it is common to just include the opening tag of each
element in the source code, so that the ruby markup is less complex and easier to read. The browser
can then fill in the full element in the rendered version.
- You need to include one `<rt>` element for each base segment/`<rb>` element that you want to annotate.

```html
<ruby>
  <rb>漢<rb>字
  <rp>(</rp><rt>kan<rt>ji<rp>)</rp>
</ruby>
```

## `<rtc>`

The HTML Ruby Text Container (`<rtc>`) element embraces semantic annotations of characters
presented in a ruby of `<rb>` elements used inside of `<ruby>` element. `<rb>` elements can have
both pronunciation (`<rt>`) and semantic (`<rtc>`) annotations.

|  |  |
| :-- | :-- |
| **Content categories** | None.
| **Permitted content** | Phrasing content or `<rt>` elements.
| **Tag omission** | The closing tag can be omitted if it is immediately followed by a `<rb>`, `<rtc>`
or `<rt>` element opening tag or by its parent closing tag. |
| **Permitted parents** | A `<ruby>` element. |
| **Permitted ARIA roles** | Any |
| **DOM interface** | `HTMLElement` |

```html
<div class="info">
  <ruby>
    <rtc>
      <rb>旧</rb><rt>jiù</rt>
      <rb>金</rb><rt>jīn</rt>
      <rb>山</rb><rt>shān</rt>
    </rtc>
    <rtc>San Francisco</rtc>
  </ruby>
</div>
```

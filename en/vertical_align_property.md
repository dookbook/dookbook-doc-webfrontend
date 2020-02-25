TOPICS: vertical-align property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Property: `vertical-align`

The **`vertical-align`** CSS property sets **vertical alignment** of an `inline`, `inline-block` or
`table-cell` box.

The `vertical-align` property can be used in two contexts:

- To vertically align an inline element's box inside its containing line box. For example, it could
be used to vertically position an [`<img>`](/en/webfrontend/<img>) in a line of text
- To vertically align the content of a cell in a table

!!! warn "Note"
    that `vertical-align` only applies to `inline`, `inline-block` and `table-cell` elements:
    you can't use it to vertically align block-level elements.

## Property Value

| Property Value | Description |
| :--- | :--- |
| **`baseline`** | Aligns the baseline of the element with the baseline of its parent. The baseline of some replaced elements, like [`<textarea>`](/en/webfrontend/<textarea>), is not specified by the HTML specification, meaning that their behavior with this keyword may vary between browsers. |
| **`sub`** | Aligns the baseline of the element with the subscript-baseline of its parent. |
| **`super`** | Aligns the baseline of the element with the superscript-baseline of its parent. |
| **`text-top`** | Aligns the top of the element with the top of the parent element's font. |
| **`text-bottom`** | Aligns the bottom of the element with the bottom of the parent element's font. |
| **`middle`** | Aligns the middle of the element with the baseline plus half the x-height of the parent. |
| length | Aligns the baseline of the element to the given length above the baseline of its parent. A negative value is allowed. |
| **`%`** | Aligns the baseline of the element to the given percentage above the baseline of its parent, with the value being a percentage of the `line-height` property. A negative value is allowed. |
| **`top`** | Aligns the top of the element and its descendants with the top of the entire line. |
| **`bottom`** | Aligns the bottom of the element and its descendants with the bottom of the entire line. |

## Examples

```css
img.top { vertical-align: text-top; }
img.bottom { vertical-align: text-bottom; }
img.middle { vertical-align: middle; }
```

```html
<div>An <img src="https://mdn.mozillademos.org/files/12245/frame_image.svg" alt="link" width="32" height="32" /> image with a default alignment.</div>
<div>An <img class="top" src="https://mdn.mozillademos.org/files/12245/frame_image.svg" alt="link" width="32" height="32" /> image with a text-top alignment.</div>
<div>An <img class="bottom" src="https://mdn.mozillademos.org/files/12245/frame_image.svg" alt="link" width="32" height="32" /> image with a text-bottom alignment.</div>
<div>An <img class="middle" src="https://mdn.mozillademos.org/files/12245/frame_image.svg" alt="link" width="32" height="32" /> image with a middle alignment.</div>
```

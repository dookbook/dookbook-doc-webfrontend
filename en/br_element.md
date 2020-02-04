TOPICS: <br>

# `<br>`

The **HTML `<br>` element** produces a line break in text (carriage-return). It is useful for
writing a poem or an address, where the division of lines is significant.

 A `<br>` element is included at each point where we want the
text to break. The text after the `<br>` begins again at the start of the next line of the text block.

!!! warn “Note"
    Do not use `<br>` to create margins between paragraphs; wrap them in [`<p>`](/en/webfrontend/<p>)
    elements and use the CSS `margin` property to control their size.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*.|
| **Permitted content** | None, it is an empty element.|
| **Tag omission** | Must have a start tag, and must not have an end tag. In XHTML documents, write this element as `<br />`. |
| **Permitted parents** | Any element that accepts *phrasing content*.|
| **Permitted ARIA roles** | Any |
| **DOM interface** | **`HTMLBRElement`** |

## Attributes

This element's attributes include the [global attributes](/en/webfrontend/HTML_Global_Attributes).

### Deprecated attributes

| Attribute Value | Description |
| :-- | :-- |
|`clear`|Indicates where to begin the next line after the break.|

## Styling with CSS

The `<br>` element has a single, well-defined purpose — to create a line break in a block of text.
As such, it has no dimensions or visual output of its own,
and there is very little you can do to style it.

You can set a `margin` on `<br>` elements themselves to increase the spacing between the
lines of text in the block, but this is a bad practice — you should use the
line-height property that was designed for that purpose.

## Examples

### Simple br

In the following example we use `<br>` elements to create
line breaks between the different lines of a postal address:

```html
Mozilla<br>
331 E. Evelyn Avenue<br>
Mountain View, CA<br>
94041<br>
USA<br>
```

## Accessibility Concerns

Creating separate paragraphs of text using `<br>` is not only bad practice, it is problematic for
people who navigate with the aid of screen reading technology. Screen readers may announce the
presence of the element, but not any content contained within `<br>`s. This can be a confusing and
frustrating experience for the person using the screen reader.

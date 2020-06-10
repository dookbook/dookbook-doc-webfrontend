TOPICS: <picture>

# `<picture>`

The **HTML `<picture>` element** contains zero or more [`<source>`](/en/webfrontend/<source>)
elements and one [`<img>`](/en/webfrontend/<img>) element to provide versions of an image for
different display/device scenarios. The browser will consider each child [`<source>`](/en/webfrontend/<source>)
element and choose the best match among them; if no matches are found, the URL of the
[`<img>`](/en/webfrontend/<img>) element's src attribute is selected. The selected image is then
presented in the space occupied by the [`<img>`](/en/webfrontend/<img>) element.

To decide which URL to load, the user agent examines each [`<source>`](/en/webfrontend/<source>)'s `srcset`,
`media`, and type attributes to select a compatible image that best matches the current
layout of the page, the characteristics of the display device, etc.

Common use cases for `<picture>`:

- Art direction — cropping or modifying images for different media conditions.
- Offering different image formats when certain formats are not supported by all browsers.

If providing higher-density versions of an image for high-DPI (Retina) display, use
`srcset` on the [`<img>`](/en/webfrontend/<img>) element instead. This lets browsers opt for lower-density
versions in data-saving modes, and you don't have to write explicit media conditions.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*, *embedded content*. |
| **Permitted content** | Zero or more [`<source>`](/en/webfrontend/<source>) elements, followed by one [`<img>`](/en/webfrontend/<img>) element, optionally intermixed with script-supporting elements. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that allows *embedded content*. |
| **Permitted ARIA roles** | None |
| **DOM interface** | **`HTMLPictureElement`** |

## Attributes

This element includes only [global attributes](/en/webfrontend/HTML_Global_Attributes).

## Usage Notes

You can use the `object-position` property to adjust the positioning of the image within the
element's frame, and the `object-fit` property to control how
the image is resized to fit within the frame.

!!! warn "Don't try this at home"
    Note: Use these properties on the child [`<img>`](/en/webfrontend/<img>) element, not the `<picture>`
    element.

## Examples

These examples demonstrate how different attributes of the [`<source>`](/en/webfrontend/<source>)
element change the selection of the image inside `<picture>`.

### The `media` attribute

The media attribute specifies a media condition (similar to a media query) that the user agent will
evaluate for each [`<source>`](/en/webfrontend/<source>) element. If the media condition evaluates
to false, its [`<source>`](/en/webfrontend/<source>) element is skipped.

```html
<picture>
  <source srcset="mdn-logo-wide.png" media="(min-width: 600px)">
  <img src="mdn-logo-narrow.png" alt="MDN">
</picture>
```

### The `type` attribute

The `type` attribute specifies a MIME type for the resource URL(s) in the
[`<source>`](/en/webfrontend/<source>) element's `srcset` attribute. If the user agent does not
support the given type, the [`<source>`](/en/webfrontend/<source>) element is skipped.

```html
​<picture>
  <source srcset="mdn-logo.svg" type="image/svg+xml">
  <img src="mdn-logo.png" alt="MDN">
</picture>
```

## Browser compatibility

| - | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
| `<picture>`| support | support | support |

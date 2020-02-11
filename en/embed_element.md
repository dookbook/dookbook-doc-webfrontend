TOPICS: <embed>

# `<embed>`

The **HTML `<embed>` element** embeds external content at the specified point in the document.
This content is provided by an external application or other source of
interactive content such as a browser plug-in.

!!! warn "Don't try this at home"
    Note: This TOPICS documents only the element that is defined as part of HTML5. It does not address
    earlier, non-standardized implementation of the element.

Keep in mind that most modern browsers have deprecated and removed support for browser plug-ins,
so relying upon `<embed>` is generally not wise if you want your site to be operable
on the average user's browser.

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*, *embedded content*, *interactive content*, *palpable content*. |
| **Permitted content** | None, it is an *empty element*. |
| **Tag omission** | Must have a start tag, and must not have an end tag. |
| **Permitted parents** | Any element that accepts *embedded content*. |
| **Permitted ARIA roles** | `application`, `document`, `img`, `presentation`|
| **DOM interface** | **`HTMLEmbedElement`** |

## Attributes

This element's attributes include the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| `height` | The displayed height of the resource, in [CSS pixels](https://drafts.csswg.org/css-values/#px). This must be an absolute value; percentages are not allowed. |
| `src` | The URL of the resource being embedded. |
| `type` | The MIME type to use to select the plug-in to instantiate. |
| `width` | The displayed width of the resource, in [CSS pixels](https://drafts.csswg.org/css-values/#px). This must be an absolute value; percentages are not allowed. |

## Usage Notes

You can use the `object-position` property to adjust the positioning of the embedded object
within the element's frame, and the `object-fit` property to control how the object's size is
adjusted to fit within the frame.

## Examples

```html
<embed type="video/quicktime" src="movie.mov" width="640" height="480">
```

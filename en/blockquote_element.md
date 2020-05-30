TOPICS: <blockquote>
        <blockquote> cite attribute

# HTML Block Quotation Element: `<blockquote>`

The **HTML block quotation element** (**`<blockquote>`**) indicates that the enclosed
text is an **extended quotation**. A URL for the source of the quotation may be given using the *`cite`*
attribute, while a text representation of the source can be given using the
*[`<cite>`](/en/webfrontend/<cite>)* element.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content Categories** | *Flow content*, *sectioning root*, *palpable content*.|
| **Permitted Content** | *Flow content*. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *flow content*.|
| **Permitted ARIA roles** | Any |
| **DOM Interface** | **`HTMLQuoteElement`** |

## Attributes

This element's attributes include the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| **`cite`** | A URL that designates a source document or message for the information quoted. This attribute is intended to point to information explaining the context or the reference for the quote.If the `cite` attribute is present, *it must be a valid URL potentially surrounded by spaces*. To obtain the corresponding citation link, the value of the attribute must be `parsed` relative to the element's `node document`. User agents may allow users to follow such citation links, but they are primarily intended for private use (e.g., by server-side scripts collecting statistics about a site's use of quotations), not for readers.|

## Usage Notes

To change the indentation applied to the quoted text, use the CSS **`margin-left`** and/or
**`margin-right`** properties, or the **`margin`** shorthand property.

To include shorter quotes inline rather than in a separate block, use the
**[`<q>`](/en/webfrontend/<q>)** (Quotation) element.

## Example

This example demonstrates the use of the `<blockquote>` element to quote a passage from
[RFC 1149](https://tools.ietf.org/html/rfc1149), A Standard for the Transmission of
IP Datagrams on Avian Carriers.

```html
<blockquote cite="https://tools.ietf.org/html/rfc1149">
  <p>Avian carriers can provide high delay, low
  throughput, and low altitude service.  The
  connection topology is limited to a single
  point-to-point path for each carrier, used with
  standard carriers, but many carriers can be used
  without significant interference with each other,
  outside of early spring.  This is because of the 3D
  ether space available to the carriers, in contrast
  to the 1D ether used by IEEE802.3.  The carriers
  have an intrinsic collision avoidance system, which
  increases availability.</p>
</blockquote>
```

## Browser compatibility

| - | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
| `<blockquote>`  | support | support | support |

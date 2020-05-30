TOPICS: <data>
        <data> value attribute

# HTML `<data>` Element

The **HTML `<data>` element** links a given content with a machine-readable translation.

!!! warn "Note"
    If the content is time- or date-related, the [`<time>`](/en/webfrontend/<time>) element must be used.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*, *palpable content*. |
| **Permitted content** | *Phrasing content*. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *phrasing content*. |
| **DOM interface** | **`HTMLDataElement`** |

## Attributes

This element's attributes include the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| **`value`** | This attribute specifies the machine-readable translation of the content of the element.

## Example

The following example displays product names but also associates each name with a product number.

```html
<p>New Products</p>
<ul>
 <li><data value="398">Mini Ketchup</data></li>
 <li><data value="399">Jumbo Ketchup</data></li>
 <li><data value="400">Mega Jumbo Ketchup</data></li>
</ul>
```

## Browser compatibility

| - | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
| `<data>`  | support | support | support |

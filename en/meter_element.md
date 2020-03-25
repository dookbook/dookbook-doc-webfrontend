TOPICS: <meter>
        <meter> value attribute
        <meter> min attribute
        <meter> max attribute
        <meter> low attribute
        <meter> high attribute
        <meter> optimum attribute
        <meter> form attribute

# HTML Meter Element: `<meter>`

The **HTML `<meter>` element** represents either **a scalar value within a known
range or a fractional value** .For example: disk usage, relevance of query results, etc.

!!! warn ""
    `<meter>` cannot be used as a progress bar, the progress bar
    [`<progress>`](/en/webfrontend/<progress>) tag.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*, *labelable content*, *palpable content*.|
| **Permitted content** | *Phrasing content*, but there must be no `<meter>` element among its descendants.|
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *phrasing content*. |
| **Permitted ARIA roles** | None |
| **DOM interface** | **`HTMLMeterElement`** |

## Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| **`value`** | The **current numeric value**. This must be between the minimum and maximum values (*`min`* attribute and *`max`* attribute) if they are specified. If unspecified or malformed, the value is *`0`*. If specified, but not within the range given by the `min` attribute and `max` attribute, the value is equal to the *nearest* end of the range. |
| **`min`** | The **lower numeric bound of the measured range**. This must be less than the maximum value (*`max`* attribute), if specified. If unspecified, the minimum value is *`0`*. |
| **`max`** | The **upper numeric bound of the measured range**. This must be greater than the minimum value (*`min`* attribute), if specified. If unspecified, the maximum value is *`1`*. |
| **`low`** | The **upper numeric bound of the low end of the measured range**. This must be greater than the minimum value (*`min`* attribute), and it also must be less than the high value and maximum value (*`high`* attribute and *`max`* attribute, respectively), if any are specified. If unspecified, or if less than the minimum value, this value is equal to the minimum value. |
| **`high`** | The **lower numeric bound of the high end of the measured range**. This must be less than the maximum value (*`max`* attribute), and it also must be greater than the low value and minimum value (*`low`* attribute and *`min`* attribute, respectively), if any are specified. If unspecified, or if greater than the maximum value, this value is equal to the maximum value. |
| **`optimum`** | This attribute indicates the **optimal numeric value**. It must be within the range (as defined by the *`min`* attribute and *`max`* attribute). When used with the *`low`* attribute and *`high`* attribute, it gives an indication where along the range is considered *preferable*. For example, if it is between the `min` attribute and the `low` attribute, then the lower range is considered preferred. |
| `form` | This attribute **associates the element with a `form` element that has ownership of this element**. |

## Simple Example

```html
<p>Heat the oven to <meter min="200" max="500"
  value="350">350 degrees</meter>.</p>
```

## High and Low Range Example

Note that in this example the `min` attribute is omitted; this is allowed, as it will default to `0`.

```html
<p>He got a <meter low="69" high="80" max="100"
  value="84">B</meter> on the exam.</p>
```

## Associated Form Example

```html
<form action="/demo_form" method="post" id="form_id">
 User name: <input type="text" name="username"><br>
 <input type="submit" value="Submit">
</form>

<meter form="form_id" name="x1" min="0" low="40" high="90" max="100" value="95"></meter>
```

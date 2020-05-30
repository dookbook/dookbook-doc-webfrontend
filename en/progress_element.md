TOPICS: <progress>
        <progress> max attribute
        <progress> value attribute

# HTML `<progress>` Element

The **HTML `<progress>` element** displays an indicator showing the **completion progress** of a task,
typically displayed as a *progress bar*.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*, *labelable content*, *palpable content*.|
| **Permitted content** | *Phrasing content*, but there must be no `<progress>` element among its descendants. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *phrasing content*. |
| **Permitted ARIA roles** | None |
| **DOM interface** | **`HTMLProgressElement`** |

## Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| **`max`** | This attribute describes **how much work the task requires**. This attribute, if present, must have a value greater than zero and be a *valid floating point number*. The default value is *`1`*. |
| **`value`** | This attribute specifies **how much of the task that has been completed**. It must be a *valid floating point number* between *`0`* and *`max`*, or between `0` and `1` if `max` is omitted. If this attribute omitted, the progress bar is *indeterminate*; this indicates that an activity is ongoing with no indication of how long it is expected to take. |

## Orient of Progress Bar

You can use the **`orient`** CSS property to specify whether the progress bar
should be rendered **horizontally** (*the default*) or **vertically**.

## Indeterminate Progress Bar

The **`:indeterminate`** pseudo-class can be used to match against *indeterminate progress bars*.
To change the progress bar to indeterminate after giving it a value you must
remove the `value` attribute with **`element.removeAttribute("value")`**.

## Examples

```html
<progress value="70" max="100">70%</progress>
```

## Browser compatibility

| - | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
| `<progress>` | support | support | support |

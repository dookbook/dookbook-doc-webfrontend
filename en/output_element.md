TOPICS: <output>
        <output> name attribute
        <output> for attribute
        <output> form attribute

# HTML Calculation Results Element: `<output>`

The **HTML Output element (`<output>`)** is a container element into which a site or app can inject
the results of a calculation or the outcome of a user action.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*, *listed*, *labelable*, *resettable form-associated element, palpable content*.|
| **Permitted content** | *Phrasing content*. |
| **Tag omission** | None, both the starting and ending tag are mandatory.|
| **Permitted parents** | Any element that accepts *phrasing content*.|
| **Permitted ARIA roles** | Any |
| **DOM interface** | **`HTMLOutputElement`** |

## Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| **`name`** | The element's name; used to identify this `<output>` during form submission.
| **`for`** | A space-separated list of other elements’ `id`s, indicating that those elements contributed input values to (or otherwise affected) the calculation.
| `form` | The form element that this element is associated with (its "form owner"). The value of the attribute must be the `id` of a [`<form>`](/en/webfrontend/<form>) element in the same document. This attribute is not needed if the `<output>` element is a descendant of a [`<form>`](/en/webfrontend/<form>) element (in which case that form is the form owner), or if the `<output>` element isn't associated with a form at all.

!!! warn "Note"
    Since the `form` attribute in `<output>` is currently not supported by almost all major browsers,
    `<output>` can no longer be written in any other position, it can only have an effect inside the
    [`<form>`](/en/webfrontend/<form>) element.

## Example

This form provides a slider whose value can range between 0 and 100. and an [`<input>`](/en/webfrontend/<input>)
element into which you can enter a second number. The two numbers are added together and the result is
displayed in the `<output>` element each time the value of any of the controls changes.

```html
<form oninput="x.value=parseInt(a.value)+parseInt(b.value)">0
  <input type="range" id="a" value="50">100
  +<input type="number" id="b" value="50">
  =<output name="x" for="a b"></output>
</form>
```

TOPICS: resize property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Property: `resize`

The CSS **`resize`** property allows you to **control the resizing of an element**.

## Property value

| Property Value | Description |
| :--- | :--- |
| **`none`** | The user cannot adjust the size of the element. |
| **`both`** | The user can adjust the **height** and **width** of the element. |
| **`horizontal`** | The user can adjust the **width** of the element. |
| **`vertical`** | The user can adjust the **height** of the element. |

!!! warn "Note"
    If the [**`overflow`**](/en/webfrontend/overflow_property) property of a **block** element is set
    to *`visible`*, then the **`resize`** property is The element is invalid.

## Examples

[*`<textarea>`*](/en/webfrontend/<textarea>) elements can be scaled by default in Gecko 2.0
(Firefox 4).You can rewrite this behavior with the following CSS code :

```css
textarea.example {
  resize: none; /* Disable resizing */
}
```

```html
<textarea class="example">Type some text here.</textarea>
```

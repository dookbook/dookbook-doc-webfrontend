TOPICS: outline-offset property

# CSS Property: `outline-offset`

The CSS **`outline-offset`** property is used to set the gap between [**`outline`**](/en/webfrontend/outline_property)
and **the edge or border of an element**.

[**`outline`**](/en/webfrontend/outline_property) is the outline of the element, suspended above the
border of the element. The element and its outline are transparent. In other words, the color between
them will inherit the background color of the parent element.

## Property value

| Property value | Description |
| :--- | :--- |
| **length** | The width between the element and the outline. Negative values draw the outline within the element. |

## Examples

```css
p {
  outline: dashed thin;
  /* Move the outline 10px away from the border */
  outline-offset: 10px;
  border:1px solid black;
}
```

```html
<p>outline: offset 10px. Border is solid and outline is dashed</p>
```

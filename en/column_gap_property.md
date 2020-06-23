TOPICS: column-gap property

# CSS Column spacing size property: `column-gap`

The CSS **`column-gap`** property is used to set the size of the gap between **element columns**.

## Property value

| Property Value | Description |
| :--- | :--- |
| **`normal`** | The browser's default spacing is used between columns. For a multi-column layout, specify it as `1em`. For all other layout types, the value is `0`. |
| **length** | **Gap size** between columns, value must be **positive number**. |
| **percentage** | Use **percentage** to define the interval between columns. Similarly, the value must be **positive number**. |

## Examples

```css
.content-box {
  column-count: 3; /* Will set the paragraph to 3 columns */
  column-gap: 40px; /* Column spacing is 40px */
}
```

```html
<p class="content-box">
  This is some multi-column text with a 40px column
  gap created with the CSS `column-gap` property.
  Don't you think that's fun and exciting? I sure do!
</p>
```

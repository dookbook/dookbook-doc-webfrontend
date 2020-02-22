TOPICS: text-shadow property

# CSS Property: `text-shadow`

The **`text-shadow`** CSS property adds shadows to text. It accepts a comma-separated list of
shadows to be applied to the text and any of its `decorations`. Each shadow is described by some
combination of X and Y offsets from the element, blur radius, and color.

This property is specified as a comma-separated list of shadows.

Each shadow is specified as two or three `<length>` values, followed optionally by a `<color>` value.
The first two `<length>` values are the `<offset-x>` and `<offset-y>` values. The third, optional,
`<length>` value is the `<blur-radius>`. The `<color>` value is the shadow's color.

When more than one shadow is given, shadows are applied front-to-back, with the first-specified
shadow on top.

This property applies to both `::first-line` and `::first-letter` pseudo-elements.

## Attribute Value

| Attribute Value | Description |
| :--- | :--- |
| `<color>` | Optional. The color of the shadow. It can be specified either before or after the offset values. If unspecified, the color's value is left up to the user agent, so when consistency across browsers is desired you should define it explicitly. |
| `<offset-x>` `<offset-y>` | Required. These `<length>` values specify the shadow's distance from the text. `<offset-x>` specifies the horizontal distance; a negative value places the shadow to the left of the text. `<offset-y>` specifies the vertical distance; a negative value places the shadow above the text. If both values are `0`, the shadow is placed directly behind the text, although it may be partly visible due to the effect of `<blur-radius>`. |
| `<blur-radius>` | Optional. This is a `<length>` value. The higher the value, the bigger the blur; the shadow becomes wider and lighter. If not specified, it defaults to `0`. |

## Examples

```css
.red-text-shadow {
  text-shadow: red 0 -2px;
}
```

```html
<p class="red-text-shadow">Sed ut perspiciatis unde omnis iste
    natus error sit voluptatem accusantium doloremque laudantium,
    totam rem aperiam, eaque ipsa quae ab illo inventore.</p>
```

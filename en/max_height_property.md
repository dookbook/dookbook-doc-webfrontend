TOPICS: max-height property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Property: `max-height`

The **`max-height`** CSS property sets **the maximum height of an element**. It prevents the used
value of the [**`height`**](/en/webfrontend/height) property from becoming larger than the value
specified for `max-height`.

## Property Value

| Property Value | Description |
| :--- | :--- |
| length | Defines the `max-height` as an absolute value. |
| **`%`** | Defines the `max-height` as a percentage of the containing block's height. |

## Examples

```html
<p>The maximum height of this segment is set to 50 px. The maximum height of this segment is set to 50 px. The maximum height of this segment is set to 50 px. The maximum height of this segment is set to 50 px. The maximum height of this segment is set to 50 px. The maximum height of this segment is set to 50 px. The maximum height of this segment is set to 50 px. The maximum height of this segment is set to 50 px. The maximum height of this segment is set to 50 px. The maximum height of this segment is set to 50 px.</p>
```

```css
p{
  max-height:50px;
  background-color:yellow;
}
```

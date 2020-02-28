TOPICS: min-height property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Property: `min-height`

The **`min-height`** CSS property sets **the minimum height of an element**. It prevents the used value
of the [**`height`**](/en/webfrontend/height_property) property from becoming smaller than the value
specified for `min-height`.

## Property Value

| Property Value | Description |
| :--- | :--- |
| length | Defines the `min-height` as an absolute value. |
| **`%`** | Defines the `min-height` as a percentage of the containing block's height. |

## Examples

```css
p {
  min-height:100px;
  background-color:yellow;
}
```

```html
<p>The minimum height of this paragraph is set to 100 px.</p>
```

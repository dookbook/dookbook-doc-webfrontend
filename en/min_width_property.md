TOPICS: min-width property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Property: `min-width`

The **`min-width`** CSS property sets **the minimum width of an element**. It prevents the used
value of the [*`width`*](/en/webfrontend/width) property from becoming smaller than the value
specified for `min-width`.

## Property Value

| Property Value | Description |
| :--- | :--- |
| length | Defines the `min-width` as an absolute value. |
| **`%`** | Defines the min-width as a percentage of the containing block's width. |

## Examples

```css
p {
  min-width:150px;
  background-color:yellow;
  width: 10px
}
```

```html
<!-- The minimum width of this paragraph is set to 150px -->
<p>min-width</p>
```

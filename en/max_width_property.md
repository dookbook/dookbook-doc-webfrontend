TOPICS: max-width property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Property: `max-width`

The **`max-width`** CSS property sets **the maximum width of an element**. It prevents the used
value of the [**`width`**](/en/webfrontend/width) property from becoming larger than the value
specified by `max-width`.

## Property Value

| Property Value | Description |
| :--- | :--- |
| length | Defines the height as an absolute value. |
| **`%`** | Defines the height as a percentage of the containing block's height. |
| **`auto`** | The browser will calculate and select a height for the specified element. |

## Examples

In this example, the `"child"` will be either `150` pixels wide or the width of the `"parent"`,
whichever is smaller:

```html
<div id="parent">
  <div id="child">
    Fusce pulvinar vestibulum eros, sed luctus ex lobortis quis.
  </div>
</div>
```

```css
#parent {
  background: lightblue;
  width: 300px;
}

#child {
  background: gold;
  width: 100%;
  max-width: 150px;
}
```

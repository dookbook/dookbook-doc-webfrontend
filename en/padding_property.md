TOPICS: padding property
        padding-top property
        padding-right property
        padding-bottom property
        padding-left property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Property: `padding`

The **`padding`** property sets **the padding of an element**. The padding area refers to the space
between **the content of an element** and **its boundary**. This property **cannot be negative**.

This is shorthand for the four padding property settings; the four padding property settings are:
**`padding-top`**, **`padding-right`**, **`padding-bottom`**, and **`padding-left`**.

## Property Value

Accept 1 ~ 4 optional parameters, each parameter takes the following values:

- When **one** value is specified, it applies the same margin to **all four sides**.
- When **two** values are specified, the first margin applies to the **top and bottom**, the second
to the **left and right**.
- When **three** values are specified, the first margin applies to the **top**, the second to the
**right and left**, the third to the **bottom**.
- When **four** values are specified, the margins apply to the **top**, **right**, **bottom**, and
**left** in that order (clockwise).

| Property Value | Description |
| :--- | :--- |
| length | Specify the fill value in specific units, such as **pixel**, **cm**, etc. The default value is `0` |
| **`%`** | Specifies padding based on a percentage of the parent element's width |

## CSS Property: `padding-top`

The **`padding-top`** CSS property sets the height of the padding area on **the top of an element**.

## CSS Property: `padding-right`

The **`padding-right`** CSS property sets the width of the padding area on **the right of an element**.

## CSS Property: `padding-bottom`

The **`padding-bottom`** CSS property sets the height of the padding area on **the bottom of an element**.

## CSS Property: `padding-left`

The **`padding-left`** CSS property sets the width of the padding area to **the left of an element**.

## Example

```html
<h4>This element has moderate padding.</h4>
<h3>The padding is huge in this element!</h3>
```

```css
h4 {
  background-color: lime;
  padding: 20px 50px;
}

h3 {
  background-color: cyan;
  padding: 110px 50px 50px 110px;
}
```

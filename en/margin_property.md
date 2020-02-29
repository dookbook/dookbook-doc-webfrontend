TOPICS: margin property
        margin-top property
        margin-right property
        margin-bottom property
        margin-left property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Property: `margin`

The **`margin`** CSS property sets **the margin area on all four sides of an element**. It is a
shorthand for **`margin-top`**, **`margin-right`**, **`margin-bottom`**, and **`margin-left`**.

The `top` and `bottom` margins have no effect on non-replaced inline elements, such as
[`<span>`](/en/webfrontend/<span>) or [`<code>`](/en/webfrontend/<code>).

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
| length | The size of the margin as a fixed value. |
| **`%`** | The size of the margin as a percentage, relative to the width of the containing block. |
| **`auto`** | The browser selects a suitable margin to use. For example, in certain cases this value can be used to center an element. |

## CSS Property: `margin-top`

The **`margin-top`** CSS property sets **the margin area on the top of an element**.

## CSS Property: `margin-right`

The **`margin-right`** CSS property sets **the margin area on the right side of an element**.

## CSS Property: `margin-bottom`

The **`margin-bottom`** CSS property sets **the margin area on the bottom of an element**.

## CSS Property: `margin-left`

The **`margin-left`** CSS property sets **the margin area on the left side of an element**.

## Example

```html
<div class="center">This element is centered.</div>

<div class="outside">This element is positioned outside of its container.</div>
```

```css
.center {
  margin: auto;
  background: lime;
  width: 66%;
}

.outside {
  margin: 3rem 0 0 -3rem;
  background: cyan;
  width: 66%;
}
```

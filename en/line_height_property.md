TOPICS: line-height property

# CSS Property: `line-height`

The **`line-height`** CSS property sets the height of a line box. It's commonly used to set the
distance between lines of text. On block-level elements, it specifies the minimum height of line
boxes within the element. On non-replaced inline elements, it specifies the height that is used to
calculate line box height.

## Property Value

| Property Value | Description |
| :--- | :--- |
| `normal` | Default. Set reasonable line spacing |
| `number` | Set a number, this number will be multiplied by the current font size to set the line spacing |
| `length` | Set a fixed line spacing |
| `%` | Percent line spacing based on the current font size |

## Basic example

```css
/* All rules below have the same resultant line height */

div { line-height: 1.2;   font-size: 10pt; }   /* number/unitless */
div { line-height: 1.2em; font-size: 10pt; }   /* length */
div { line-height: 120%;  font-size: 10pt; }   /* percentage */
div { font: 10pt/1.2  Georgia,"Bitstream Charter",serif; } /* font shorthand */
```

It is often more convenient to set `line-height` by using the `font` shorthand as shown above, but
this requires the font-family property to be specified as well.

## Prefer unitless numbers for `line-height` values

This example shows why it is better to use `<number>` values instead of `<length>` values. We will
use two [`<div>`](/en/webfrontend/<div>) elements. The first, with the green border, uses a unitless
`line-height` value. The second, with the red border, uses a `line-height` value defined in `em`s.

```css
.green {
  line-height: 1.1;
  border: solid limegreen;
}

.red {
  line-height: 1.1em;
  border: solid red;
}

h1 {
  font-size: 30px;
}

.box {
  width: 18em;
  display: inline-block;
  vertical-align: top;
  font-size: 15px;
}
```

```html
<div class="box green">
 <h1>Avoid unexpected results by using unitless line-height.</h1>
  length and percentage line-heights have poor inheritance behavior ...
</div>

<div class="box red">
 <h1>Avoid unexpected results by using unitless line-height.</h1>
  length and percentage line-heights have poor inheritance behavior ...
</div>

<!-- The first <h1> line-height is calculated from its own font-size   (30px × 1.1) = 33px  -->
<!-- The second <h1> line-height results from the red div's font-size  (15px × 1.1) = 16.5px,  probably not what you want -->
```

TOPICS: z-index property

# CSS Property: `z-index`

The **`z-index`** CSS property sets the `z-order` of a positioned element and its descendants or `flex`
items. Overlapping elements with a larger `z-index` cover those with a smaller one.

For a positioned box (that is, one with any `position` other than `static`), the `z-index` property specifies:

1. The stack level of the box in the current stacking context.
1. Whether the box establishes a local stacking context.

The `z-index` property is specified as either the keyword `auto` or an `<integer>`.

## Property Value

| Property Value | Description |
| :--- | :--- |
| **`auto`** | The box does not establish a new local stacking context. The stack level of the generated box in the current stacking context is the same as its parent's box. |
| **`inherit`** | This `<integer>` is the stack level of the generated box in the current stacking context. The box also establishes a local stacking context in which its stack level is `0`. This means that the `z-indexes` of descendants are not compared to the `z-indexes` of elements outside this element. |

## Examples

```html
<div class="dashed-box">Dashed box
  <span class="gold-box">Gold box</span>
  <span class="green-box">Green box</span>
</div>
```

```css
.dashed-box {
  position: relative;
  z-index: 1;
  border: dashed;
  height: 8em;
  margin-bottom: 1em;
  margin-top: 2em;
}
.gold-box {
  position: absolute;
  z-index: 3; /* put .gold-box above .green-box and .dashed-box */
  background: gold;
  width: 80%;
  left: 60px;
  top: 3em;
}
.green-box {
  position: absolute;
  z-index: 2; /* put .green-box above .dashed-box */
  background: lightgreen;
  width: 20%;
  left: 65%;
  top: -25px;
  height: 7em;
  opacity: 0.9;
}
```

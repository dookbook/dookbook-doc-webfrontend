TOPICS: grid-auto-flow property

# CSS Property: `grid-auto-flow`

CSS **`grid-auto-flow`** property **controls how the automatic layout algorithm works**, precisely
specifying how **elements are automatically arranged in the grid**.

This property has two forms:

- A single keyword: one of **`row`**, **`column`**, or **`dense`**.
- Two keywords: **`row`** **`dense`** or **`column`** **`dense`**.

## Property value

| Property value | Description |
| :--- | :--- |
| **`row`** | This keyword specifies that the automatic layout algorithm arranges elements by padding line by line, adding new lines when necessary. If neither **`row`** nor **`column`** is specified, the default is **`row`**. |
| **`column`** | This keyword specifies that the auto layout algorithm arranges elements by column-by-column padding, adding new columns when necessary. |
| **`dense`** | This keyword specifies that the auto-layout algorithm uses a "dense" stacking algorithm. If a slightly smaller element appears in the back, it will try to fill the gap left in the grid. Doing so will fill in the gaps left by the larger elements, but it may also cause the original order to be disturbed. If you omit it, a "sparse" algorithm is used. When laying out elements in the grid, the layout algorithm will only move "forward", and will never go back to fill in the gaps. This ensures that all auto-layout elements appear "in order", even though it may leave blank spaces filled by subsequent elements. |

## Examples

```html
<div id="grid">
  <div id="item1"></div>
  <div id="item2"></div>
  <div id="item3"></div>
  <div id="item4"></div>
  <div id="item5"></div>
</div>
<select id="direction" onchange="changeGridAutoFlow()">
  <option value="column">column</option>
  <option value="row">row</option>
</select>
<input id="dense" type="checkbox" onchange="changeGridAutoFlow()">
<label for="dense">dense</label>
```

```css
#grid {
  height: 200px;
  width: 200px;
  display: grid;
  grid-gap: 10px;
  grid-template: repeat(4, 1fr) / repeat(2, 1fr);
  grid-auto-flow: column;  /* Or 'row','row dense','column dense' */
}

#item1 {
  background-color: lime;
  grid-row-start: 3;
}

#item2 {
  background-color: yellow;
}

#item3 {
  background-color: blue;
}

#item4 {
  grid-column-start: 2;
  background-color: red;
}

#item5 {
  background-color: aqua;
}
```

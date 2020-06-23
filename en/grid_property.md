TOPICS: grid property

# CSS Property: `grid`

**`grid`** is a shorthand CSS property that can be used to set the following properties:

**Explicit grid**Properties [**`grid-template-rows`**](/en/webfrontend/grid-template-rows_property),
[**`grid-template-columns`**](/en/webfrontend/grid-template-columns_property) and
[**`grid-template-areas`**](/en/webfrontend/grid-template-areas_property).

**Implicit grid** properties [**`grid-auto-rows`**](/en/webfrontend/grid-auto-rows_property),
[**`grid-auto-rowumns`**](/en/webfrontend/grid-auto-columns_property) and [**`grid-auto-flow`**](/en/webfrontend/grid-auto-flow_property).

**Pitch** Properties [**`grid-column-gap`**](/en/webfrontend/grid-column-gap_property) and [**`grid-row-gap`**](/en/webfrontend/grid-row-gap_property).

!!! warn "Note"
    You can only declare **explicit** or **implicit grid** in one **`grid`** property. As with other
    shorthand propertys, if a secondary property is not declared, it will use the initial value. In
    addition, although this shorthand statement cannot set a grid slot (**gutter**), the slot will
    be reset by this statement.

## Property value

| Property value | Description |
| :--- | :--- |
| **grid-template** | Defined `grid-template`, which contains `grid-template-columns`, `grid-template-rows` and `grid-template-areas`. |
| **grid-template-rows / auto-flow && dense? grid-auto-columns?** | Set the automatic flow by setting the row track explicitly through the `grid-template-rows` property (the `grid-template-columns` property is set to `none`), and through the `grid-auto-columns` how to automatically repeat the column track (At the same time, the `grid-auto-rows` property is set to `auto`). The `grid-auto-flow` property is set to `column` accordingly, and can be accompanied by `dense`. <br><br>All remaining `grid` secondary propertys are reset to their initial values. |
| **auto-flow && dense? grid-auto-rows? / grid-template-columns** | Set the automatic flow by setting the column track explicitly through the `grid-template-columns` property (the `grid-template-rows` property is set to `none`), and use `grid-auto-rows` to specify how to automatically repeat the row track (At the same time, the `grid-auto-columns` property is set to `auto`). The `grid-auto-flow` property is also set to `row` accordingly, and may be accompanied by `dense`. <br><br>All remaining `grid` secondary propertys are reset to their initial values. |

## Grammar

```css
/* <'grid-template'> values */
grid: none;
grid: "a" 100px "b" 1fr;
grid: [linename1] "a" 100px [linename2];
grid: "a" 200px "b" min-content;
grid: "a" minmax(100px, max-content) "b" 20%;
grid: 100px / 200px;
grid: minmax(400px, min-content) / repeat(auto-fill, 50px);

/* <'grid-template-rows'> /
   [ auto-flow && dense? ] <'grid-auto-columns'>? values */
grid: 200px / auto-flow;
grid: 30% / auto-flow dense;
grid: repeat(3, [line1 line2 line3] 200px) / auto-flow 300px;
grid: [line1] minmax(20em, max-content) / auto-flow dense 40%;

/* [ auto-flow && dense? ] <'grid-auto-rows'>? /
   <'grid-template-columns'> values */
grid: auto-flow / 200px;
grid: auto-flow dense / 30%;
grid: auto-flow 300px / repeat(3, [line1 line2 line3] 200px);
grid: auto-flow dense 40% / [line1] minmax(20em, max-content);

/* Global values */
grid: inherit;
grid: initial;
grid: unset;
```

## Examples

```html
<div id="container">
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
</div>
```

```css
#container {
  display: grid;
  grid: repeat(2, 60px) / auto-flow 80px;
}

#container > div {
  background-color: #8ca0ff;
  width: 50px;
  height: 50px;
}
```

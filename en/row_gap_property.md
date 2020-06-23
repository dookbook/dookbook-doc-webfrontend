TOPICS: row-gap property

# CSS Property: `row-gap`

The CSS **`row-gap`** property is used to set the size of the gap between **row elements**.

!!! warn "Note"
    CSS Grid Layout was originally defined with the **`grid-row-gap`** property, and is now gradually
    replaced by **`row-gap`**. However, in order to be compatible with browsers that do not support
    the **`row-gap`** property, you need to use the prefixed property.

## Property value

| Property Value | Description |
| :--- | :--- |
| **length-percentage** | Represents the width of the space between lines. **percentage** represents the percentage relative to the grid container. |

## Flex layout

```html
<div id="flexbox">
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
</div>
```

```css
#flexbox {
  display: flex;
  flex-wrap: wrap;
  width: 300px;
  row-gap: 20px;
}

#flexbox > div {
  background-color: lime;
  flex: 1 1 auto;
  width: 100px;
  height: 50px;

}
```

## Grid layout

```html
<div id="grid">
  <div></div>
  <div></div>
  <div></div>
</div>
```

```css
#grid {
  display: grid;
  height: 200px;
  grid-template-columns: 200px;
  grid-template-rows: repeat(3, 1fr);
  row-gap: 20px;
}

#grid > div {
  background-color: lime;
}
```

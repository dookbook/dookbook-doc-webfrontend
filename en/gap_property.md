TOPICS: gap property

# CSS property: `gap`

CSS **`gap`** property is used to set the gap between grid rows and columns** (gutters), the property
is [**`row-gap`**](/en/webfrontend/row-gap_property) and [**`column-gap`**](/en/webfrontend/column-gap_property)
short form.

```css
grid-gap: 0;
grid-gap: 10%;
grid-gap: 1em;
grid-gap: 10px 20px;
grid-gap: calc(20px + 10%);
```

!!! warn "Note"
    CSS Grid Layout was originally defined with the **`grid-gap`** property, and is now gradually
    replaced by **`gap`**. However, in order to be compatible with browsers that do not support the
    **`gap`** property, you need to use the prefixed property as in the example above.

This property is used to represent the values of [**`row-gap`**](/en/webfrontend/row-gap_property) and
[**`column-gap`**](/en/webfrontend/column-gap_property) , And [**`column-gap`**](/en/webfrontend/column-gap_property)
is optional, if [**`column-gap`**](/en/webfrontend/column-gap_property) If it is missing, it will be
set to the same value as [**`row-gap`**](/en/webfrontend/row-gap_property).

[**`row-gap`**](/en/webfrontend/row-gap_property) and [**`column-gap`**](/en/webfrontend/column-gap_property)
can be used **length** or **percentage** to express.

## Property value

| Property value | Description |
| :--- | :--- |
| **length** | The width of the gap between grid lines. |
| **percentage** | The gap width of the grid line directly, as a percentage of the grid container. |

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
  gap: 20px 5px;
}

#flexbox > div {
  border: 1px solid green;
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
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
</div>
```

```css
#grid {
  display: grid;
  height: 200px;
  grid-template: repeat(3, 1fr) / repeat(3, 1fr);
  gap: 20px 5px;
}

#grid > div {
  background-color: lime;
}
```

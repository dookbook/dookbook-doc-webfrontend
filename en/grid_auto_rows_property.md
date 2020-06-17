TOPICS: grid-auto-rows property

# CSS Property: `grid-auto-rows`

The CSS **`grid-auto-rows`** property is used to specify the implicitly created rows **track size**.

If the grid element positioned in a row does not use `grid-template-rows` to specify the size, a `grid`
track is implicitly created to save it. This may occur when the display locates a line that is out of
range, or when an additional line is created by the automatic placement algorithm.

## Property value

| Property value | Description |
| :--- | :--- |
| **length** | A non-negative length. |
| **percentage** | A non-negative `percentage` value relative to the grid window block size. If the block size of the grid container is uncertain, the percentage value will be treated as `auto`. |
| **flex** | The non-negative dimension in units of `fr` specifies the elasticity factor of the orbit. Each `flex`-sized track squeezes a portion of the remaining space in proportion to its elasticity factor. <br>When used outside the `minmax()` symbol, it means that the minimum value is `auto` (Example: `minmax(auto, flex)`). |
| **`max-content`** | Keywords, indicating that the largest occupied space among the grid elements determines the size of the track. |
| **`min-content`** | The keyword specifies that the smallest element in the grid element determines the size of the track. |
| **`minmax(min, max)`** | Function symbol, define a size range not less than `min` and not more than `max`. If `max` is smaller than `min`, then `max` will be ignored and the function will be recorded as `min`. As the maximum value, the `flex` value sets the elasticity factor of the track. As the minimum value, it will be treated as `0` (or the minimum content-when the grid container specifies the size as the minimum content). |
| **`auto`** | The keyword, when used to specify the maximum value, is consistent with the maximum content, when used to specify the minimum value, it represents the maximum value of the minimum size of all grid elements in the track (by [`min-width`](/en/webfrontend/min-width_property)/[`min-height`](/en/webfrontend/min-height_property) specified).|

!!! warn "Note"
    **`auto`** track size (and only **`auto`** track size) can be used with [**`align-content`**](/en/webfrontend/align-content_property)
    and [** `justify-content`**](/en/webfrontend/justify-content_property) property is used.

## Examples

```html
<div id="grid">
  <div id="item1"></div>
  <div id="item2"></div>
  <div id="item3"></div>
</div>
```

```css
#grid {
  width: 200px;
  display: grid;
  grid-template-areas: "a a";
  grid-gap: 10px;
  grid-auto-rows: 100px;
}

#grid > div {
  background-color: lime;
}
```

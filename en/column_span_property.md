TOPICS: column-span property

# CSS Property: `column-span`

The CSS **`column-span`** property specifies how many columns an element should **cross**.

## Property value

| Property Value | Description |
| :--- | :--- |
| **`none`** | The element **does not span multiple columns**. |
| **`all`** | Element **Across all columns**. Before the element appears, the content that appears in the normal flow before the element is automatically balanced between all columns. This element establishes a new block format context. |

## Examples

```css
article {
  columns: 3; /* The column is divided into 3 columns */
}

h2 {
  column-span: all; /* Across all columns */
}
```

```html
<article>
  <h2>Header spanning all of the columns</h2>
  <p>
     The h2 should span all the columns. The rest
     of the text should be distributed among the columns.
  </p>
  <p>This is a bunch of text split into three columns using the CSS `columns` property. The text is equally distributed over the columns.</p>
  <p>This is a bunch of text split into three columns using the CSS `columns` property. The text is equally distributed over the columns.</p>
  <p>This is a bunch of text split into three columns using the CSS `columns` property. The text is equally distributed over the columns.</p>
  <p>This is a bunch of text split into three columns using the CSS `columns` property. The text is equally distributed over the columns.</p>
</article>
```

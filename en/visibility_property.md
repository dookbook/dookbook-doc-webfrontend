TOPICS: visibility property

# CSS Show Or Hide Element Property: `visibility`

The **`visibility`** CSS property **shows** or **hides** an element **without changing the
layout of a document**. The property can also hide **rows** or **columns** in a [*`<table>`*](en/webfrontend/<table>).

## Property Value

| Property Value | Description |
| :--- | :--- |
| **`visible`** | The element box is visible. |
| **`hidden`** | **Hidden element**, but the layout of other elements does not change, which is equivalent to this element becoming transparent. Note that if its child element is set to `visibility: visible`, the child element will still be visible |
| **`collapse`** | Hide the **row** or **column** of the table, **and take up no space** (equivalent to using *`display: none`* on the rows/columns of the table). However, if you set [*`<table>`*](/en/webfrontend/<table>) to a height, **what space will it still occupy** |

## Example

```css
h1.visible { visibility: visible }
h1.hidden { visibility: hidden }

/* Example of deleting table rows and columns */
table {
  height: 300px;
}

table, th, td {
  border: 1px solid black;
}

tr.collapse {
  visibility: collapse;
}
```

```html
<h1 class="visible">This is a visible heading</h1>
<h1 class="hidden">This is an invisible heading</h1>
<p>Notice that the invisible heading still takes up space.</p>

<!-- Example of deleting table rows and columns -->
<table>
  <tr>
    <th>Firstname</th>
    <th>Lastname</th>
  </tr>
  <tr>
    <td>Peter</td>
    <td>Griffin</td>
  </tr>
  <tr class="collapse">
    <td>Lois</td>
    <td>Griffin</td>
  </tr>
  <tr>
    <td>Peter</td>
    <td>Griffin</td>
  </tr>
  <tr>
    <td>Peter</td>
    <td>Griffin</td>
  </tr>
</table>
```

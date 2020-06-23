TOPICS: caption-side property

# CSS Poperty: `caption-side`

The CSS **`caption-side`** property will put the table header [*`<caption>`*](/en/webfrontend/<caption>)
in the specified position. But the specific display position is related to the value of the table's
*`writing-mode`* property.

## Property value

| Property value | Description |
| :--- | :--- |
| **`top`** | Defaults. Position the table title **on the table**. |
| **`bottom`** | Position the table title **below the table**. |

## Examples

```css
.top caption {
  caption-side: top;
}

.bottom caption {
  caption-side: bottom;
}

table {
  border: 1px solid red;
}

td {
  border: 1px solid blue;
}
```

```html
<table class="top">
  <caption>Caption ABOVE the table</caption>
  <tr>
    <td>Some data</td>
    <td>Some more data</td>
  </tr>
</table>

<br>

<table class="bottom">
  <caption>Caption BELOW the table</caption>
  <tr>
    <td>Some data</td>
    <td>Some more data</td>
  </tr>
</table>
```

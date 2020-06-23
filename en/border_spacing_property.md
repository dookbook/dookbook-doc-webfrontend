TOPICS: border-spacing property

# CSS Property: `border-spacing`

The CSS **`border-spacing`** property specifies **the distance between the borders of adjacent cells**
(only in border separation mode). Equivalent to the *`cellspacing`* property in HTML, but the second
optional value can be used to set the vertical spacing different from the horizontal spacing.

**`border-spacing`** value also applies to the outer border of the table, that is, the distance
between the border of the table and the cells in the first row, first column, last row, and last
column is determined by The corresponding (horizontal or vertical) border spacing of the table is
filled with the relevant (`top`, `right`, `bottom` or `left`) on the table.

This property is only applicable when **`border-collapse`** value is **`separate`**.

!!! warn "Note"
    **`border-spacing`** Its syntax value can only have **one** or **two**. **Single** statement
    **both top, bottom, left, and right margins are the same**. At that time **two values**
    **the previous one is the left and right distance**, the latter value **the upper and lower distance**.
    See the example below for details.

## Property value

| Property value | Description |
| :--- | :--- |
| **length** | A length value describing the **horizontal** and **vertical distance** between cells. It is only used in single value syntax. |
| **horizontal** | A length value describing the **horizontal distance** between cells ** in two adjacent columns. It is only used in double-valued syntax. |
| **vertical** | A length value describing the **vertical distance** between adjacent **cells** in two rows. It is only used in double-valued syntax. |
| **`inherit`** | For a keyword that represents the calculated value of **`border-spacing`** of the parent element, the parent element must have **`border-spacing`** applied. |

## Examples

```css
table.ex1 {
  border-collapse: separate;
  border-spacing: 10px;
}

table.ex2 {
  border-collapse: separate;
  border-spacing: 10px 50px;
}
```

```html
<table class="ex1" border="1">
  <tr>
    <td>Peter</td>
    <td>Griffin</td>
  </tr>
  <tr>
    <td>Lois</td>
    <td>Griffin</td>
  </tr>
</table>

<br>

<table class="ex2" border="1">
  <tr>
    <td>Cleveland</td>
    <td>Brown</td>
  </tr>
  <tr>
    <td>Glenn</td>
    <td>Quagmire</td>
  </tr>
</table>
```

TOPICS: position property
        top property
        right property
        bottom property
        left property
        z-index property
        float property
        clear property
        display property

# CSS Position

CSS has three basic positioning mechanisms: **normal flow**, **floating**, and **absolute positioning**.

Unless specifically specified, all boxes are positioned in the normal stream. That is, the position
of an element in a normal stream is determined by the position of the element in (X) HTML.

Block-level boxes are arranged one after another from top to bottom. The vertical distance between
the boxes is calculated from the vertical margins of the boxes.

Inline boxes are arranged horizontally in a row. You can adjust their spacing using horizontal
padding, borders, and margins. However, vertical padding, borders, and margins do not affect the
height of inline boxes. A horizontal box formed by one line is called a line box, and the height of
the line box is always high enough to accommodate all the inline boxes it contains. However, setting
the line height can increase the height of this box.

Set the positioning mechanism properties as follows

| Attributes | Description |
| :--- | :--- |
| **`position`** | Specify the **positioning method** of the element in the document. The **`top`**, **`right`**, **`bottom`**, and **`left`** properties determine the final position of the element. |
| **`top`** | The **Top Margin Boundary** of a positioned element and its containing block **Offset Between Top Boundaries**, this property is invalid for non-positioned elements. |
| **`right`** | An anchored element's **right margin boundary** and its containing block **offset between the right margin**, this property has no effect on unpositioned elements. |
| **`bottom`** | An anchored element **lower margin boundary** and its containing block **offset between lower borders**, this property is not valid for unpositioned elements. |
| **`left`** | An anchored element's **left margin boundary** and its containing block **offset between the left margin**, this property has no effect on unpositioned elements. |
| **`z-index`** | Specify **target element level**. **When elements overlap**, **`z-index`** **larger** elements will cover **smaller** elements to be displayed on the upper layer. |
| **`float`** | Specifies **the element should follow its container** **left** or **right float**, allowing text and inline elements to surround it |
| **`clear`** | Specify **element to clear float** |
| **`display`** | Sets whether the element is considered **block element** or **embedded element** and the layout used for its child elements, such as flow layout, grid, or flex. |

## `position` Attribute value

| Attribute Value | Description |
| :--- | :--- |
| **`absolute`** | Generate **absolute positioning** element relative to the first parent element other than `static` positioning |
| **`fixed`** | Generates **fixed positioning** elements, positioning relative to the browser window |
| **`relative`** | Generates **relatively positioned** elements, positioned relative to their normal position |
| **`static`** | Defaults. No positioning, elements appear in normal flow (ignore `top`, `bottom`, `left`, `right` or `z-index` declarations) |
| **`sticky`** | Sticky positioning based on where the user scrolled |

## `top`, `right`, `right`, `left` Attribute value

| Attribute Value | Description |
| :--- | :--- |
| **`auto`** | Defaults. Calculate **top right bottom left** position via browser. |
| **`%`** | Sets the **top right bottom left** position as a percentage of the containing element. You can use negative values. |
| length | Use **px**, **em**, etc. to set the element's **top right bottom left** position. You can use negative values.|

## `z-index` Attribute value

| Attribute Value | Description |
| :--- | :--- |
| **`auto`** | **default**. The stacking order is equal to the parent element.|
| integer | integer is the **stacking level** of the generated box in the current stacking context |

## `float` Attribute value

| Attribute Value | Description |
| :--- | :--- |
| **`none`** | Defaults. The element **does not float** and appears where it appears in the text. |
| **`left`** | The element **floats to the left**. |
| **`right`** | The element **floats to the right**. |
| **`inline-start`** | A keyword indicating that the element must float to the beginning of the block container it is in, left in the `ltr` script and right in the `rtl` script.|
| **`inline-end`** | A keyword indicating that the element must float to the end of the block container it is in. It is the right side in the `ltr` script and the left side in the `rtl` script.|

## `clear` Attribute value

| Attribute Value | Description |
| :--- | :--- |
| **`none`** | Defaults. Allow floating elements to appear on both sides. |
| **`left`** | Clear the **left floating** element. |
| **`right`** | Clear the **right floating** element. |
| **`both`** | Clear the **left and right float** elements. |
| **`inline-start`** | This keyword indicates that the element moves down to clear the float on the starting side of its containing block. That is, floating on the left or right of an area. |
| **`inline-end`** | The keyword indicates that the element is moved down to clear the floating point at the end of its containing block, that is, floating to the right or left of an area. |

## `display` Attribute value

| Attribute Value | Description |
| :--- | :--- |
| **`none`** | This element will not be displayed |
| **`block`** | This element will appear as a **block-level element** with a line break before and after this element |
| **`inline`** | Default. This element will be displayed as **inline element** with no line breaks before and after the element |
| **`inline-block`** | **Inline block elements** |
| **`list-item`** | This element is **displayed as a list** |
| **`run-in`** | This element is displayed as a **block-level element** or **inline element** depending on the context |
| **`compact`** | CSS has value compact, but has been removed from CSS2.1 due to lack of extensive support |
| **`marker`** | There are value markers in CSS, but they have been removed from CSS2.1 due to lack of extensive support |
| **`table`** | This element will be displayed as a **block-level table** (similar to `<table>`) with newlines before and after |
| **`inline-table`** | This element will be displayed as a **inline table** (like `<table>`), with no line breaks before or after the table |
| **`table-row-group`** | This element is displayed as a group of **one** or **more lines** (similar to `<tbody>`) |
| **`table-header-group`** | This element is displayed as **one** or **grouping of multiple rows** (similar to `<thead>`) |
| **`table-footer-group`** | This element will be displayed as **one** or **group of multiple lines** (like `<tfoot>`) |
| **`table-row`** | This element will be displayed as **a table row** (like `<tr>`) |
| **`table-column-group`** | This element is displayed as **one** or **grouping of multiple columns** (like `<colgroup>`) |
| **`table-column`** | This element will be displayed as **a cell column** (like `<col>`) |
| **`table-cell`** | This element will be displayed as **a table cell** (like `<td>` and `<th>`) |
| **`table-caption`** | This element is displayed as **a table title** (similar to `<caption>`) |
| **`inherit`** | Specifies that the value of the `display` attribute should be inherited from the parent element |

## Example

```html
<div class="a">
  <p class="a-child1">This is a piece of textA</p>
  <p class="a-child2">This is a piece of textB</p>
</div>

<div class="b">
  <p class="b-child1">This is a piece of textA</p>
  <p class="b-child2">This is a piece of textB</p>
  <p class="b-child3">This is a piece of textC</p>
</div>

<div class="c">
  <p class="c-child1">This is a piece of textA</p>
  <span class="c-child2">This is a piece of textb</span>
</div>
```

```css
.a {
  width: 300px;
  height: 300px;
  position: relative; /* Add relative definition to parent element, child element will be positioned relative to parent */
  background: #000;
}

.a-child1 {
  background: red;
  width: 300px;
  height: 150px;
  position: absolute; /* Adds absolute positioning to the element, positioning relative to the parent element, or positioning relative to the body if the parent element is not positioned */
  left: 0; /* 0 from the left of the parent element */
  top: 20px; /* 20px from the parent element */
}

.a-child2 {
  background: blue;
  width: 200px;
  height: 150px;
  position: absolute;
  right: 0;
  bottom: 20px;
  z-index: 1; /* Add a level to this element, it will be higher than the .a-child1 element, and will overlap on top of the .a-child1 element */
}

.b {
  width: 300px;
  height: 200px;
  background: indianred;
  margin: 20px 0;
}

.b-child1 { /* Add a left float to the p tag, the text will be displayed to the left, and it will no longer occupy a line */
  float: left;
  background: red;
}

.b-child2 { /* Clear the float of the p tag, it will not affect the other floating elements */
  clear: both;
  background: goldenrod;
}

.b-child3 { /* Add a right float to the p tag, the text will be displayed to the right, it will no longer occupy a line */
  float: right;
  background: blue;
}

.c {
  background: indianred;
  width: 300px;
  height: 200px;
}

.c-child1 {
  display: inline; /* Will turn <p> block-level elements into inline elements */
  background: khaki;
}

.c-child2 {
  display: block; /* Turns <span> inline elements into block elements */
  background: lawngreen;
}
```

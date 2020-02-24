TOPICS: writing-mode property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Property: `writing-mode`

The **`writing-mode`** CSS property sets whether lines of **text are laid out horizontally or vertically**,
**as well as the direction in which blocks progress**. When set for an entire document, it should
be set on the root element ([`<html>`](/en/webfrontend/<html>) element for HTML documents).

This property specifies the block flow direction, which is the direction in which block-level
containers are stacked, and the direction in which inline-level content flows within a block container.
Thus, it also determines the ordering of block-level content.

## Property Value

| Property Value | Description |
| :--- | :--- |
| **`horizontal-tb`** | For ltr scripts, content flows horizontally from left to right. For rtl scripts, content flows horizontally from right to left. The next horizontal line is positioned below the previous line.
| **`vertical-rl`** | For ltr scripts, content flows vertically from top to bottom, and the next vertical line is positioned to the left of the previous line. For rtl scripts, content flows vertically from bottom to top, and the next vertical line is positioned to the right of the previous line.
| **`vertical-lr`** | For ltr scripts, content flows vertically from top to bottom, and the next vertical line is positioned to the right of the previous line. For rtl scripts, content flows vertically from bottom to top, and the next vertical line is positioned to the left of the previous line.

## Examples

```css
table, td, th {
  border: 1px solid black;
}

table {
  border-collapse: collapse;
  width: 100%;
}
.example.Text1 span, .example.Text1 {
  writing-mode: horizontal-tb;
  -webkit-writing-mode: horizontal-tb;
  -ms-writing-mode: horizontal-tb;
}

.example.Text2 span, .example.Text2 {
  writing-mode: vertical-lr;
  -webkit-writing-mode: vertical-lr;
  -ms-writing-mode: vertical-lr;
}

.example.Text3 span, .example.Text3 {
  writing-mode: vertical-rl;
  -webkit-writing-mode: vertical-rl;
  -ms-writing-mode: vertical-rl;
}
```

```html
<table>
  <tr>
    <th>value</th>
    <th>Vertical script</th>
    <th>Horizontal script</th>
    <th>Mixed script</th>
  </tr>
  <tr>
    <td>horizontal-tb</td>
    <td class="example Text1"><span>我家没有电脑。</span></td>
    <td class="example Text1"><span>Example text</span></td>
    <td class="example Text1"><span>1994年に至っ    </span></td>
  </tr>
  <tr>
    <td>vertical-lr</td>
    <td class="example Text2"><span>我家没有电脑。</span></td>
    <td class="example Text2"><span>Example text</span></td>
    <td class="example Text2"><span>1994年に至っては</span></td>
  </tr>
  <tr>
    <td>vertical-rl</td>
    <td class="example Text3"><span>我家没有电脑。</span></td>
    <td class="example Text3"><span>Example text</span></td>
    <td class="example Text3"><span>1994年に至っては</span></td>
  </tr>
</table>
```

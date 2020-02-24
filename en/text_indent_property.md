TOPICS: text-indent property

# CSS Property: `text-indent`

The **`text-indent`** CSS property sets the **length of empty space (indentation) that is put before
lines of text in a block**. Horizontal spacing is with respect to the left (or right, for
right-to-left layout) edge of the containing block-level element's content box.

## Property Value

| Property Value | Description |
| :--- | :--- |
| length | Defines a fixed indentation. Default: `0`. |
| **`%`** | Defines the indentation based on a percentage of the width of the parent element. |

## Examples

```css
p {
  text-indent: 5em;
  background: powderblue;
}
```

```html
<p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy
    nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat.</p>
<p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy
    nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat.</p>
```

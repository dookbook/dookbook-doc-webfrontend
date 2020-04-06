TOPICS: caret-color property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Insert Cursor Color Property: `caret-color`

**`caret-color`** attribute is used to define the color of **insert cursor** (caret), the insert
cursor mentioned here is the one in the editable area of the webpage, used to indicate the user ’s
The one that is inserted into it flashes like a vertical bar `|`.

## Property Value

| Property Value | Description |
| :--- | :--- |
| **`auto`** | The default color, at this time the browser should use `currentcolor` as the color of the insertion cursor, but the browser may also adjust the color according to the current background color, shadow color, etc. to ensure that the insertion cursor has a good Visibility.|
| **color** | The color value of the specified insertion cursor |

## Example

```html
<input type="text" value="Please enter content">
```

```css
input {
  caret-color: red;
}
```

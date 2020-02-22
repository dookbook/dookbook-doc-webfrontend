TOPICS: color property

# CSS Property: `color`

**`color`** property specifies the color of the text

## Attribute Value

| Attribute Value | Description |
| :--- | :--- |
| `color_name` | Specifies that the color value is the color of the color name (such as **red**). |
| `hex_number` | Specifies the color with a hexadecimal value (e.g. **#ff0000**).|
| `rgb_number` | Specifies the color value of the **rgb** code (eg **rgb(255, 0, 0)**).|
| `inherit` | Specifies that color should be inherited from the parent element. |

## Examples

```css
p { color: red; }
p { color: #f00; }
p { color: #ff0000; }
p { color: rgb(255,0,0); }
p { color: rgb(100%, 0%, 0%); }
p { color: hsl(0, 100%, 50%); }

/* 50% translucent */
p { color: #ff000080; }
p { color: rgba(255, 0, 0, 0.5); }
p { color: hsla(0, 100%, 50%, 0.5); }
```

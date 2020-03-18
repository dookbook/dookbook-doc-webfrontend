TOPICS: clip-path property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Shear Properties: `clip-path`

The **`clip-path`** CSS property creates a clipping region that sets what part of an element should
be shown. Parts that are inside the region are shown, while those outside are hidden.

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **margin-box** | Uses the `margin` box as the reference box |
| **border-box** | Uses the `border` box as the reference box |
| **padding-box** | Uses the `padding` box as the reference box |
| **content-box** | Uses the `content` box as the reference box |
| **fill-box** | Uses the object bounding box as the reference box |
| **stroke-box** | Uses the stroke bounding box as the reference box. |
| **view-box** | Uses the nearest SVG viewport as the reference box. If a `viewBox` attribute is specified for the element creating the SVG viewport, the reference box is positioned at the origin of the coordinate system established by the `viewBox` attribute and the dimension of the size of the reference box is set to the width and height values of the `viewBox` attribute |
| **`none`** | No clipping path is created |

## Example

```html
<img id="clipped" src="https://mdn.mozillademos.org/files/12668/MDN.svg"
    alt="MDN logo">
```

```css
#clipped {
  margin-bottom: 20px;
  clip-path: circle(100px at 110px 100px);
}
```

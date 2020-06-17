TOPICS: filter property

# CSS Property: `filter`

The CSS **`filter`** property applies graphic effects such as **blur** or **color shift** to the
element. Filters are usually used to adjust the rendering of images, backgrounds and borders.

## Property value

| Property value | Description |
| :--- | :--- |
| **`none`** | The default value has no effect. |
| **`blur(px)`** | Set Gaussian Blur to the image. A value of "radius" sets the standard deviation of the Gaussian function, or how many pixels are fused together on the screen, so the larger the value, the more blurred; <br> If there is no set value, the default is `0`; this parameter can be set CSS length values, but percentage values are not accepted.|
| **`brightness(%)`** | Apply a linear multiplication to the picture to make it look brighter or darker. If the value is `0%`, the image will be completely black. If the value is `100%`, there is no change in the image. The other values correspond to the linear multiplier effect. Values above 100% are also possible, the image will be brighter than before. If there is no set value, the default is `1`. |
| **`contrast(%)`** | Adjust the contrast of the image. If the value is 0%, the image will be completely black. The value is `100%` and the image is unchanged. The value can exceed `100%`, which means that a lower contrast will be used. If no value is set, the default is `1`. |
| **`drop-shadow(h-shadow v-shadow blur spread color)`** | Set a shadow effect on the image. Shadows are composited under the image, and can have blurriness, an offset version of the mask map that can be drawn in a specific color. The function accepts a value of type **shadow** (defined in the context of CSS3), except that the "inset" keyword is not allowed. This function is very similar to the existing **`box-shadow`** property; the difference is that through filters, some browsers provide hardware acceleration for better performance. **shadow** parameters are as follows:<br><br>**offset-x** **offset-y** (required)<br>This are the two **length** values ​​that set the shadow offset . **offset-x** Set the horizontal distance. Negative values ​​cause the shadow to appear to the left of the element. **offset-y** Set the vertical distance. Negative values ​​cause shadows to appear above the element. <br>If both values ​​are `0`, the shadow appears directly behind the element (if **blur-radius** and/or **spread-radius** are set, there will be a blur effect). <br><br>**blur-radius** (optional)<br>This is the third **length** value. The larger the value, the more blurred, the shadow will become larger and lighter. Negative values ​​are not allowed. If not set, the default is `0` (the shadow's border is sharp). <br><br>**spread-radius** (optional)<br>This is the fourth **length** value. A positive value will expand and enlarge the shadow, and a negative value will reduce the shadow. If not set, the default is `0` (the shadow will be the same size as the element). <br>Note: WebKit, and some other browsers do not support the fourth length, and will not render if added. <br><br> **color** (optional)<br>If not set, the color value is based on the browser. In Gecko (Firefox), Presto (Opera) and Trident (Internet Explorer), the value of the `color` property is applied. In addition, if the color value is omitted, the shadow in WebKit is transparent. |
| **`grayscale(%)`** | Convert the image to a grayscale image. The value defines the scale of the conversion. If the value is `100%`, it will be completely converted to grayscale image, and if the value is `0%`, the image will not change. Values between `0%` and `100%` are linear multipliers of the effect. If not set, the default value is `0`. |
| **`hue-rotate(deg)`** | Apply hue rotation to the image. A value of "angle" sets the color circle angle value at which the image will be adjusted. If the value is `0deg`, the image has no change. If the value is not set, the default value is `0deg`. Although this value has no maximum value, a value exceeding `360deg` is equivalent to another round. |
| **`invert(%)`** | Reverse the input image. The value defines the scale of the conversion. The value of `100%` is completely reversed. If the value is `0%`, the image has no change. Values between `0%` and `100%` are linear multipliers of the effect. If the value is not set, the value defaults to `0`. |
| **`opacity(%)`** | Transparency of the image. The value defines the scale of the conversion. A value of `0%` is completely transparent, and a value of `100%` means no change in the image. Values between `0%` and `100%` are linear multipliers of the effect, which is also equivalent to multiplying the number of image samples. If the value is not set, the default value is `1`. This function is very similar to the existing **`opacity`** property, the difference is that through `filter`, some browsers provide hardware acceleration to improve performance. |
| **`saturate(%)`** | Convert image saturation. The value defines the scale of the conversion. A value of `0%` means completely unsaturated, and a value of `100%` means no change in the image. Other values are linear multipliers of the effect. Values above `100%` are allowed, and there is a higher degree of saturation. If the value is not set, the default value is `1`. |
| **`sepia(%)`** | Convert the image to sepia. The value defines the scale of the conversion. A value of `100%` is completely dark brown, and a value of `0%` does not change the image. Values between `0%` and `100%` are linear multipliers of the effect. If not set, the default value is `0`. |
| **`url()`** | The URL function accepts an XML file, which sets an SVG filter, and can contain an anchor point to specify a specific filter element. <br>For example: `filter: url(SVG-url#element-id)`. |
| **`initial`** | Set the property to the default value. |
| **`inherit`** | Inherit this property from the parent element. |

## Examples

```html
<img src="pineapple.jpg" alt="Pineapple" width="300" height="300">
<img class="blur" src="pineapple.jpg" alt="Pineapple" width="300" height="300">
<img class="brightness" src="pineapple.jpg" alt="Pineapple" width="300" height="300">
<img class="contrast" src="pineapple.jpg" alt="Pineapple" width="300" height="300">
<img class="grayscale" src="pineapple.jpg" alt="Pineapple" width="300" height="300">
<img class="huerotate" src="pineapple.jpg" alt="Pineapple" width="300" height="300">
<img class="invert" src="pineapple.jpg" alt="Pineapple" width="300" height="300">
<img class="opacity" src="pineapple.jpg" alt="Pineapple" width="300" height="300">
<img class="saturate" src="pineapple.jpg" alt="Pineapple" width="300" height="300">
<img class="sepia" src="pineapple.jpg" alt="Pineapple" width="300" height="300">
<img class="shadow" src="pineapple.jpg" alt="Pineapple" width="300" height="300">
```

```css
img {
  width: 33%;
  height: auto;
  float: left;
}

.blur {
  -webkit-filter: blur(4px);
  filter: blur(4px);
}

.brightness {
  -webkit-filter: brightness(0.30);
  filter: brightness(0.30);
}

.contrast {
  -webkit-filter: contrast(180%);
  filter: contrast(180%);
}

.grayscale {
  -webkit-filter: grayscale(100%);
  filter: grayscale(100%);
}

.huerotate {
  -webkit-filter: hue-rotate(180deg);
  filter: hue-rotate(180deg);
}

.invert {
  -webkit-filter: invert(100%);
  filter: invert(100%);
}

.opacity {
  -webkit-filter: opacity(50%);
  filter: opacity(50%);
}

.saturate {
  -webkit-filter: saturate(7);
  filter: saturate(7);
}

.sepia {
  -webkit-filter: sepia(100%);
  filter: sepia(100%);
}

.shadow {
  -webkit-filter: drop-shadow(8px 8px 10px green);
  filter: drop-shadow(8px 8px 10px green);
}
```

TOPICS: background property
        background-clip property
        background-color property
        background-image property
        background-origin property
        background-position property
        background-repeat property
        background-size property
        background-attachment property
        background-blend-mode property

# CSS Background (`background`)

CSS allows application **solid colors as background** and also allows
**background images to create fairly complex effects**.

CSS's capabilities in this area go far beyond HTML.

## CSS Background Attribute

| Attribute | Description |
| :--- | :--- |
| **`background`** | **Abbreviated attributes**, for one-time **Centralized definition of various background attributes** .It is recommended to follow this order:`background:bg-color bg-image position/bg-size bg-repeat bg-origin bg-clip bg-attachment initial/inherit;`It can also be omitted in more cases.|
| **`background-clip`** | Sets whether the element's **background image or color extends below the border**. |
| **`background-color`** | Sets the **background color of the element**. The value of the attribute is:<br> *`color`* :**Background color value** ,See [CSS Color](/en/webfrontend/css_color) for details.<br> *`transparent`*（Default): Specify the background color as **transparent**, which is *keyword*, and choose either of `color`;<br> *`inherit`* ：Specifies the background color, which should be inherited from the parent element. |
| **`background-image`** | Set **one** or **multiple background images** to use.(Multiple backgrounds are separated by commas.) |
| **`background-origin`** | Set the **positioning area of the background image** .|
| **`background-position`** | For each background image **set the initial position**. This position is relative to the position layer defined by *`background-origin`* .|
| **`background-repeat`** | Defines **how the background image is repeated**. The background image can be along the **horizontal axis**, **vertical axis**, **the two axes repeat**, or **do not repeat at all** .|
| **`background-size`** | Set **background image size**. The picture can retain its original size, or be stretched to a new size, or scaled to the available space of the element while maintaining its original proportions .|
| **`background-attachment`** | Determines whether the position of the background image is fixed in the viewport or scrolls with the block that contains it .|
| **`background-blend-mode`** | Set the element's **background image to blend with each other and the element's background color** .|

## `background-clip` Attribute Value

| Attribute Value | Description |
| :--- | :--- |
| **`border-box`** | Defaults. The background extends beyond the border (but below the border) .|
| **`padding-box`** | The background extends to the outer edge of the inner margin. It will not be drawn to the border. |
| **`content-box`** | The background is cropped to the outer edge of the content area. |

## `background-image` Attribute Value

| Attribute Value | Description |
| :--- | :--- |
| **url('URL')** | **Image URL** .|
| **`none`** | **No image background is displayed**. This is the default. |
| `linear-gradient()` | The function is used to create a linear gradient "image".Grammar:`background-image: linear-gradient(direction(角度), color-stop1, color-stop2, ...);`|
| `radial-gradient()` |Radial gradients create "images".Value:<br> **`shape`** ：Type of circle. `ellipse` (Default): Specify the radial gradient of the ellipse.`circle`: Specify the radial gradient of the circle.<br> **`size`** ：Define the size of the gradient,Value:`farthest-corner` (Default): Specify the radius of the radial gradient from the center of the circle to the farthest angle from the center of the circle.`closest-side`: Specify the radius length of the radial gradient from the center of the circle to the side closest to the center of the circle.`closest-corner`: Specify the radius length of the radial gradient from the center of the circle to the corner closest to the center of the circle.`farthest-side`:Specifies the radius length of the radial gradient from the center of the circle to the edge furthest from the center of the circle.<br> **`position`** : Define the position of the gradient.Value:`center`(Default): Set the center to the ordinate value of the center of the radial gradient circle.`top`: Set the top to the ordinate value of the center of the radial gradient circle.`bottom`: Set the bottom to the ordinate value of the center of the radial gradient circle.<br>**`start-color, ..., last-color`**：Used to specify the start and end colors of the gradient.|
| `repeating-radial-gradient()` | The function is used to create repeated radial gradient "images". Its possible values are the same as `radial-gradient ()`.|
| `repeating-linear-gradient()`| The function is used to create a repeating linear gradient "image".Value:<br>**`angle`**: Define the angle direction of the gradient. From 0deg to 360deg, the default is 180deg.<br> **`side-or-corner`** Specify the starting position of the linear gradient. It consists of two keywords: the first is to specify the horizontal position (`left` or `right`), and the second is to specify the vertical position (`top` or `bottom`). The order is arbitrary, and each keyword is optional.<br>**`start-color, ..., last-color`** : Specify the start and end colors of the gradient, consisting of the color value and the stop position (optional, specified in percentage).|
 |`inherit` |Specifies the background color, which should be inherited from the parent element. (rarely use)|

## `background-origin` Attribute Value

| Attribute Value | Description |
| :--- | :--- |
| **`padding-box`** | The background image is placed with the **`border`** area as a reference |
| **`border-box`** | The background image is placed with the **`padding`** area as a reference |
| **`content-box`** | The background image is placed with the **`content`** area as a reference |

## `background-position` Attribute Value

| Attribute Value | Description |
| :--- | :--- |
| **`left`**,**`top`**<br>**`left`**,**`center`**<br>**`left`**,**`bottom`**<br>**`right`**, **`top`**<br>**`right`**,**`center`**<br>**`right`**,**`bottom`**<br>**`center`**,**`top`**<br>**`center`**,**`center`**<br>**`center`**,**`bottom`** | If only one keyword is specified, the other values will be **`center`**; <br> For example: `background-position: top;` will be equivalent to `background-position: top center;`. |
| `x%`,`y%` | The first value is the **horizontal** position, and the second value is the **vertical**. The top left corner is `0% 0%`. Bottom right corner is `100% 100%`. If only one value is specified, the other values will be `50%`. The default value is: `0% 0%` .|
| `xpos`,`ypos` | The first value is the **horizontal** position, and the second value is the **vertical**. The upper left corner is `0`. The unit can be pixels (`0px 0px`) or any other [CSS unit](/en/webfrontend/css_length_unit). If only one value is specified, the other values will be `50%`. You can mix `%` and `positions` .|
| **`inherit`** | Inherit from parent element .|

## `background-repeat` Attribute Value

| Attribute Value | Description |
| :--- | :--- |
| **`repeat`** | The background image will repeat in the **vertical** and **horizontal directions**. This is the default. |
| **`repeat-x`** | Only **the horizontal position repeats** the background image. |
| **`repeat-y`** | Only **vertical position will repeat** the background image. |
| **`no-repeat`** | No duplication. |
| **`inherit`** | Inherit from parent element. |

## `background-size` Attribute Value

| Attribute Value | Description |
| :--- | :--- |
| length | Set the background image **height** and **width**. The **first** value sets the **width** and the **second** value sets the **height**. If only one value is given, the second is set to **`auto`** (automatic). |
| **`%`** | The **percentage** relative to the background positioning area is calculated. The **first** value sets the **width** and the **second** value sets the **height**. If only one value is given, the second is set to **`auto`** (automatic). |
| **`cover`** | At this time, the **aspect ratio** of the image is maintained and the image is scaled to the **minimum size** that will **fully cover the background positioning area** .|
| **`contain`** | At this time, the **aspect ratio** of the image is maintained and the image is scaled to the **maximum size** of **suitable for the background positioning area**. |

## `background-attachment` Attribute Value

| Attribute Value | Description |
| :--- | :--- |
| **`scroll`** | The background image scrolls with the **rest of the page**. This is the default. |
| **`fixed`** | The background image is **fixed**. |
| **`inherit`** | Inherit from parent element. |

## `background-blend-mode` Attribute Value

| Attribute Value | Description |
| :--- | :--- |
| **`normal`** | Defaults. Set **normal blend** mode. |
| **`multiply`** | **Positive film overlay** mode. |
| **`screen`** | **Filter color** mode. |
| **`overlay`** | **Overlay** mode. |
| **`darken`** | **Darken** mode. |
| **`lighten`** | **Lighten** mode. |
| **`color-dodge`** | **Color Dodge** mode.|
| **`saturation`** | **Saturation** mode. |
| **color** | **Color** mode. |
| **`luminosity`** | **Brightness** mode. |

## Example

```css
div {
  border:1px solid black;
  padding: 30px;
  height: 200px;
  background-image: url('sealing.png'); /* Add a background image to the div */
  background-repeat: no-repeat; /* Picture is not tiled */
  background-position: left top; /* Picture is on the top left */
  background-origin: content-box; /* Specify image in content area */
  background-clip: padding-box; /* Cropped background in */
  background-attachment: fixed; /* The image will not scroll with the content, the background-origin property has no effect when using this property */
  background-size: 100px; /* Set the image size to 100px */
  background-color:rgb(255, 0, 0); /* Set background color */
  background-blend-mode: multiply; /* Set picture overlays */
}
```

```html
<div>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.</div>
```

TOPICS: CSS Box Model
        margin property
        margin-top property
        margin-right property
        margin-bottom property
        margin-left property
        padding property
        padding-top property
        padding-right property
        padding-bottom property
        padding-left property
        border property
        border-width property
        border-style property
        border-color property
        border-top property
        border-top-color property
        border-top-style property
        border-top-width property
        border-right property
        border-right-color property
        border-right-style property
        border-right-width property
        border-bottom property
        border-bottom-color property
        border-bottom-style property
        border-bottom-width property
        border-left property
        border-left-color property
        border-left-style property
        border-left-width property

# CSS Box Model (`margin`, `border`, `padding`)

**CSS box model** (a design and *layout* glossary) is essentially a box that encapsulates surrounding
HTML elements. It includes: **margin**, **border**, **padding**, and actual **content**.

The following picture illustrates the Box Model:

![CSS Box Model](/media/webfrontend__css-box-model.png)

Explanation of different parts:

| Part | Comment | CSS Properties Involved |
| :--: | :-- | :-- |
| **Margin** | Outside the border area. Margin has no background color, it is completely transparent. | [*`margin`*](#margin-properties) etc. |
| **Border** | The padding and content around the border. The border is affected by the background color of the box. | [*`border`*](#border-properties) etc. |
| **Padding** | Clear the area around the content. Will be affected by the background color of the box fill. | [*`padding`*](#padding-properties) etc. |
| **Content** | The content of the box, displaying text or images | *`width`*, *`height`*. More details of [CSS Dimension](/en/webfrontend/CSS_dimension) |

## Size of Box Model

When you specify the `width` and `height` properties of a CSS element, you just set the
width and height of the content area.
To know that for full-size elements, you must also add *padding*,
*borders*, and *margins*.

In the example below, the actual width of the element is `280px`, and the actual width of box is `300px`.

```css
div {
  width: 250px;
  padding: 10px;
  border: 5px solid gray;
  margin: 10px;
}
```

The actual size of the element is

- element width = `width` + `padding-left` + `padding-right` + `border-left` + `border-right`
- element height = `height` + `padding-top` + `padding-bottom` + `border-top` + `border-bottom`

And the size the box needs to be

- box width = element width + `margin-left` + `margin-right`
- box height = element height + `margin-top` + `margin-bottom`

## Margin and Padding

### Margin Properties

| Property | Description |
| :--: | :--- |
| **`margin`** | *Shorthand* property to set values the thickness of the margin area. **Negative values** for margin properties are allowed, but there may be implementation-specific limits. |
| **`margin-top`** | Element's **top margin** |
| **`margin-right`** | Element's **right margin** |
| **`margin-bottom`** | Element's **bottom margin** |
| **`margin-left`** | Element's **left margin** |

### Padding Properties

| Property | Description |
| :--: | :--- |
| **`padding`** | Shorthand property to set values the thickness of the padding area. The value **may not** be negative. |
| **`padding-top`** | Element's **top padding** |
| **`padding-right`** | Element's **right padding** |
| **`padding-bottom`** | Element's **bottom padding** |
| **`padding-left`** | Element's **left padding** |

### Property Values of `margin` and `padding`

They both have property values as follows:

| Property Value | Description |
| :--: | :--- |
| **length** | a length unit. See [CSS Length Unit](/en/webfrontend/CSS_length_unit) |
| **`%`** | Percentage value based on parent element. |

!!! warn ""
    The *length* and *`%`* of `margin` value can be **negative**; however, the *`padding`* **cannot be**.

`margin` has another value **`auto`**,
which lets the browser automatically select a suitable value to apply.

### Shorthand Properties for `margin` and `padding`

`margin`, `padding` accept 1 ~ 4 optional parameters.

`margin` for example:

```css
/* 4 parameters: top right bottom left (clockwise order) */
margin: 10px 5px 15px 20px;

/* same with */
margin-top: 10px;
margin-right: 5px;
margin-bottom: 15px;
margin-left: 20px;
```

```css
/* 3 parameters: top left=right bottom */
margin: 10px 5px 15px;

/* same with */
margin-top: 10px;
margin-left: 5px;
margin-right: 5px;
margin-bottom: 15px;
```

```css
/* 2 parameters: top=bottom left=right */
margin: 10px 5px;

/* same with */
margin-top: 10px;
margin-bottom: 10px;
margin-left: 5px;
margin-right: 5px;
```

```css
/* 1 parameter: top=bottom=left=right */
/* margins of top, bottom, left and right are all 10px */
margin: 10px;

/* same with */
margin-top: 10px;
margin-bottom: 10px;
margin-left: 10px;
margin-right: 10px;
```

## Border

| Property | Description |
| :--: | :--- |
| **`border`** | Shorthand properties. |
| **`border-width`** | Set the **width** of the border. Having four extended properties: *`border-top-width`*, *`border-right-width`*, *`border-bottom-width`*, *`border-left-width`*. |
| **`border-style`** | Set the **style** of the border. Having four extended properties: *`border-top-style`*, *`border-right-style`*, *`border-bottom-style`*, *`border-left-style`*. |
| **`border-color`** | Set the **color** of the border. Having four extended properties: *`border-top-color`*, *`border-right-color`*, *`border-bottom-color`*, *`border-left-color`*. |
| **`border-top`** | Set the **top** of the border. An abbreviation of the three properties *`border-top-color`*, *`border-top-style`*, and *`border-top-width`*. |
| **`border-right`** | Set the **right** of the border. An abbreviation of three properties: *`border-right-color`*, *`border-right-style`*, and *`border-right-width`*. |
| **`border-bottom`** | Set the **bottom** of the border. An abbreviation of the three properties of *`border-bottom-color`*, *`border-bottom-style`*, and *`border-bottom-width`*. |
| **`border-left`** | Set the **left** of the border. An abbreviation of three properties: *`border-left-color`*, *`border-left-style`*, and *`border-left-width`*. |

### Border Width `border-width`

| `border-width` Value | Description |
| :--: | :--- |
| **`thin`** | border's width is **thin**. |
| **`medium`** | (*Default*) border's width is **medium**. |
| **`thick`** | border's width is **thick**. |
| **length** | border's width is **custom**, using [CSS Length Unit](/en/webfrontend/CSS_Length_Unit) |
| **`inherit`** | inherited from the parent element |

The `border-width` property sets widths of borders with four directions.

```css
/* 4 parameters: top right bottom left (clockwise order) */
border-width: thin medium thick 10px;

/* same with */
border-top-width: thin;
border-right-width: medium;
border-bottom-width: thick;
border-left-width: 10px;
```

```css
/* 3 parameters: top left=right bottom */
border-width: thin medium thick;

/* same with */
border-top-width: thin;
border-right-width: medium;
border-left-width: medium;
border-bottom-width: thick;
```

```css
/* 2 parameters: top=bottom left=right */
border-width: thin thick;

/* same with */
border-top-width: thin;
border-bottom-width: thin;
border-left-width: thick;
border-right-width: thick;
```

```css
/* 1 parameter: top=bottom=left=right */
/* border width of top, bottom, left and right are all thin */
border-width: thin;

/* same with */
border-top-width: thin;
border-bottom-width: thin;
border-left-width: thin;
border-right-width: thin;
```

### Border Style `border-style`

| Property Value | Description |
| :--: | :--- |
| **`none`** | Define borderless. |
| **`hidden`** | Same as *`none`*, except for tables: `hidden` is used to resolve border conflicts. |
| **`dotted`** | **dotted line** |
| **`dashed`** | **dashed line** |
| **`solid`** | **solid line** |
| **`double`** | **double line** |
| **`groove`** | **sculpted** border |
| **`ridge`** | **embossed** border |
| **`inset`** | **immersed** border |
| **`outset`** | **outset** border |
| **`inherit`** | inherited from the parent element |

The `border-style` property sets styles of borders with four directions.

```css
/* 4 parameters: top right bottom left (clockwise order) */
border-style: dotted solid double dashed;

/* same with */
border-top-style: dotted;
border-right-style: solid;
border-bottom-style: double;
border-left-style: dashed;
```

```css
/* 3 parameters: top left=right bottom */
border-style: dotted solid double;

/* same with */
border-top-style: dotted;
border-right-style: solid;
border-left-style: solid;
border-bottom-style: double;
```

```css
/* 2 parameters: top=bottom left=right */
border-style: dotted solid;

/* same with */
border-top-style: dotted;
border-bottom-style: dotted;
border-left-style: solid;
border-right-style: solid;
```

```css
/* 1 parameter: top=bottom=left=right */
/* border style of top, bottom, left and right are all solid */
border-style: solid;

/* same with */
border-top-style: solid;
border-bottom-style: solid;
border-left-style: solid;
border-right-style: solid;
```

### Border Color `border-color`

| Property Value | Description |
| :--: | :--- |
| **color** | Border color, full list of color values is in [CSS color](/en/webfrontend/css_color) |
| **`transparent`** | The color of the specified border is **transparent**. This is the *default*. |
| **`inherit`** | Inherit from parent element |

The `border-color` property sets colors of borders with four directions.

```css
/* 4 parameters: top right bottom left (clockwise order) */
border-color: #111 #222 #333 #444;

/* same with */
border-top-color: #111;
border-right-color: #222;
border-bottom-color: #333;
border-left-color: #444;
```

```css
/* 3 parameters: top left=right bottom */
border-color: #111 #222 #333;

/* same with */
border-top-color: #111;
border-left-color: #222;
border-right-color: #222;
border-bottom-color: #333;
```

```css
/* 2 parameters: top=bottom left=right */
border-color: #111 #222;

/* same with */
border-top-color: #111;
border-bottom-color: #111;
border-left-color: #222;
border-right-color: #222;
```

```css
/* 1 parameter: top=bottom=left=right */
/* border color of top, bottom, left and right are all #111 */
border-color: #111;

/* same with */
border-top-color: #111;
border-bottom-color: #111;
border-left-color: #111;
border-right-color: #111;
```

### `border` Shorthand Property

| Property Value | Description |
| :--: | :--- |
| **border-width** | Specify the **width** of the border. |
| **border-style** | Specify the **style** of the border. |
| **border-color** | Specify the **color** of the border. |
| **`inherit`** | Inherited from the parent element. |

```css
border: 10px solid #111;
```

## CSS Border image properties `border-image`

The CSS **`border-image`** property **draws an image around the border** on a given element. It
replaces the element's (regular border). Are **`border-image-source`**, **`border-image-slice`**,
**`border-image-width`**, **`border-image-outset`** and **`border-image-repeat`** Abbreviation for attribute.

### Border image resource `border-image-source`

CSS property **`border-image-source`** resource for declaring the border image of the element

| Property Value | Description |
| :--- | :--- |
| **`none`** | No images are used |
| **image** | Border use image path |

### Border image segmentation `border-image-slice`

After referencing the border picture through **`border-image-source`**, the **`border-image-slice`**
property will divide the picture **into 9 regions**: four corners, four sides ( edges) and the center
area. Four slice lines, set a given distance from their respective sides, control the size of the area.

![border-image-slice](/media/webfrontend__border-image-slice.png)

The figure above illustrates the location of each area.

- Regions 1-4 are corner regions. Each one is used once to form the corner points of the final
boundary image.
- Region 5-8 edge region. Repeat, scale or modify them in the final border image to match the size
of the element.
- Region 9 is the middle region. It is discarded by default, but if the keyword `fill` is set, it is
used as the background image.

The middle area will not be used by the border, but will be used as `background-image` when the `fill`
keyword is set. This keyword can be set anywhere in the property (front, back, or between two values)

| Property Value | Description |
| :--- | :--- |
| **number** | The number represents the pixels of the image (bitmap image) or the coordinates of the vector (if the image is a vector image) |
| **`%`** | The percentage image size is relative: horizontally offset image width, vertical offset image height |
| **`fill`** | Keep the middle part of the image |

### Border image width `border-image-width`

**`border-image-width`** Defines the image **border width**. If `border-image-width` is greater than
the specified *`border-width`*, then it will expand internally (`padding`/`content`).

| Property Value | Description |
| :--- | :--- |
| **number** | Indicates a multiple of the corresponding border-width |
| **`%`** | Boundary image area size: area of width of lateral offset, area of height of vertical offset |
| **`auto`** | If specified, the width is the intrinsic width or height of the corresponding image slice |

### Can exceed the size of the border box `border-image-outset`

The **`border-image-outset`** property defines the border image **which can exceed the size of the
border box**.

| Property Value | Description |
| :--- | :--- |
| **length** | The size of the border image starts in one dimension, which is a number with units |
| **number** | The size of the border image starts as a multiple of the corresponding border width of the element. For example, if the border width of an element is: `1em 2px 0 1.5rem` and `border-image-outset: 2`, the final `border-image-outset` will be calculated as `2em 4px 0 3rem` |

### Fill border image `border-image-repeat`

**`border-image-repeat`** Definition **how the picture fills the border**. Or for a single value,
set all borders; or for two values, set horizontal and vertical borders, respectively

| Property Value | Description |
| :--- | :--- |
| **`stretch`** | **Stretch the picture** to fill the border |
| **`repeat`** | **Tile the picture** to fill the border |
| **`round`** | Tile the image. When you can't tile an integer number of times, enlarge or reduce the image according to the situation |
| **`space`** | Tile the image. When tiling cannot be performed an integer number of times, a blank gap is used to fill the image around (the image will not be enlarged or reduced) |

## CSS 圆角属性 `border-radius`

The CSS **`border-radius`** property sets the element's **outer border rounded corners**. Are
**`border-top-left-radius`**, **`border-top-right-radius`**, **`border-bottom-right-radius`**,
and **`border-bottom -left-radius`** Abbreviation for attribute

| Property | Description |
| :--- | :--- |
| **`border-top-left-radius`** | Defines the shape of the border in the upper left corner |
| **`border-top-right-radius`** | Defines the shape of the border in the upper right corner |
| **`border-bottom-right-radius`** | Defines the shape of the bottom right corner border |
| **`border-bottom-left-radius`** | Defines the shape of the bottom-left border |

| Property Value | Description |
| :--- | :--- |
| length | Define the shape of the curve |
| **`%`** | Use `%` to define the shape of the corner |

## Example

```html
<div>
  <p class="a">This is a section of content A</p>
  <p class="b">This is a section of content B</p>
</div>
```

```css
* { margin: 0; padding: 0;}

div {
  border: 1px solid #333; /* Define a 1px solid border with a red border for the element */
  margin: 10px; /* Define a margin of 10px for the element from the four borders */
  padding: 10px 20px; /* Define an inner margin of 10px from the top and bottom and 20px from the left and right of the element */
  border-image-source: url('border.png'); /* Specify the border picture address */
  border-image-slice: 30; /* Split picture */
  border-image-width: 10px; /* Specify the picture size as 10px */
  border-image-repeat: repeat; /* Tile picture */
  border-image-outset: 10px; /* Define image 10px beyond border box */
}

div p.a {
  background: red;
  padding: 10px 20px 5px 30px; /* Define padding 10px above, 20px right, 5px down, 30px left */
  margin-bottom: 20px; /* Define the margin at 20px*/
  border-radius: 20px; /* Define rounded corners as 20px */
}

div p.b {
  background: red;
  padding: 10px 20px 5px; /* Define the padding to be 10px on the top, 20px on the left and 5px on the bottom */
}
```

## References

- [W3C CSS 2.2 Specification - Box Model](https://www.w3.org/TR/CSS22/box.html)

TOPICS: transform property
        transform-style property
        transform-origin property
        transform-box property
        perspective property
        perspective-origin property
        backface-visibility property
        translate property

# CSS 2D/3D Transform Property (`transform`)

## CSS Property `transform`

The CSS **`transform`** property allows you to **rotate**, **scale**, **tilt** or **translate** a
given element. This is achieved by modifying the coordinate space of the CSS visual formatting model.

!!! warn "Note"
    Only elements positioned by the box model can be transformed. As a rule of thumb, if the element
    has `display: block`, the element is positioned by the box model.

| Property Value | Description |
| :--- | :--- |
| **`none`** | Do not apply any transformation |
| **`matrix(n,n,n,...)`** | Define a 2D transformation using a matrix of six values |
| **`matrix3d(n,n,n,...)`** | Define a 3D transformation using a 4x4 matrix of 16 values |
| **`translate(x,y)`** | Define 2D transformation |
| **`translate3d(x,y,z)`** | Defining 3D transformations |
| **`translateX(x)`** | Define the transformation, just use the values of the X axis |
| **`translateY(y)`** | Define the transformation, just use the values of the Y axis |
| **`translateZ(z)`** | Define a 3D transformation, just use the Z-axis values |
| **`scale(x[,y]?)`** | Define 2D scaling transformation |
| **`scale3d(x,y,z)`** | Defining 3D scaling transformations |
| **`scaleX(x)`** | Define the scaling transformation by setting the value of the X axis |
| **`scaleY(y)`** | Define the scaling transformation by setting the value of the Y axis |
| **`scaleZ(z)`** | Define the 3D scale transformation by setting the value of the Z axis |
| **`rotate(angle)`** | Define 2D rotation, specify angle in parameters |
| **`rotate3d(x,y,z,angle)`** | Define 3D rotation |
| **`rotateX(angle)`** | Define 3D rotation along the X axis |
| **`rotateY(angle)`** | Define 3D rotation along the Y axis |
| **`rotateZ(angle)`** | Define 3D rotation along the Z axis |
| **`skew(x-angle,y-angle)`** | Define a 2D tilt transformation along the X and Y axes |
| **`skewX(angle)`** | Define a 2D tilt transformation along the X axis |
| **`skewY(angle)`** | Define a 2D tilt transformation along the Y axis |
| **`perspective(n)`** | Define perspective views for 3D transform elements |

## CSS Property: `transform-style`

CSS property **`transform-style`** Sets whether the element's child elements are in **3D space** or **plane**.

If you select a plane, the child elements of the element will not have a 3D occlusion relationship.

Since this attribute is **not inherited**, it must be set for all non-leaf child elements of the element.

| Property Value | Description |
| :--- | :--- |
| **`flat`** | Sets the child elements of the element to be in the element's **plane** |
| **`preserve-3d`** | Indicates that the element's children should be located in **3D space** |

## CSS Property: `transform-origin`

**`transform-origin`** CSS properties let you change an element **the origin of the deformation**.

The transformation start point is the point at which the transformation is applied. For example,
the transformation origin of the *`rotate()`* function is the center of rotation. (The application
principle of this attribute is to first transform the element using the assignment of this attribute,
transform it, and then use the value of this attribute to convert the element back)

The `transform-origin` attribute can be specified using one, two, or three values, where each value
represents an offset. Offsets that are not explicitly defined will be reset to their corresponding
initial values.

If two or more values are defined and there are no keywords, or the only keyword used is `center`,
the first value represents **horizontal offset** and the second value represents **vertical Offset**.

- One value
    - Must be one of length, percentage, or `left`, `center`, `right`, `top`, `bottom`
- Two value
    - One of them must be the length, percentage, or one of the `left`, `center`, `right` keywords.
    - The other must be one of length, percentage, or `top`, `center`, `bottom` keywords.
- Three value：
    - The first two values are used the same as when there are only two values.
    - The third value must be a length. It always represents the Z-axis offset.

| Property Value | Description |
| :--- | :--- |
| **x-offset** | Defines the length or percentage offset of the deformation center from the left side of the box model |
| **offset-keyword** | One of `left`, `right`, `top`, `bottom` or `center`, which defines the corresponding deformation center offset |
| **y-offset** | Defines the length or percentage offset of the deformation center from the top of the box model |
| **x-offset-keyword** | One of `left`, `right` or `center`, which defines the corresponding deformation center offset |
| **y-offset-keyword** | One of `top`, `bottom` or `center`, which defines the corresponding deformation center offset |
| **z-offset** | Defines the length (not percent) offset of the deformation center from the user's line of sight (`z=0`) |

Keywords are a convenient shorthand equivalent to the following percentage values:

| Keywords | Value |
| --- | --- |
| `left` | `0%` |
| `center` | `50%` |
| `right` | `100%` |
| `top` | `0%` |
| `bottom` | `100%` |

# CSS Property: `transform-box`

**`transform-box`** attributes define the layout boxes associated with the two attributes
*`transform`* and *`transform-origin`*.

| Property Value | Description |
| :--- | :--- |
| `border-box` | The border is used as a reference box. The `border-box` of a table is the border of the table box, not the border of the table. |
| `fill-box` | Use object bounding box as reference box |
| `view-box` | Use the nearest SVG view as the reference frame. If the `viewBox` property is specified for the SVG viewport creation element, the reference box is positioned at the origin of the coordinate system established by the `viewBox` property, and the dimension of the reference box is set to the width and height values of the `viewBox` property |

## CSS Property: `perspective`

CSS property **`perspective`** specifies how 3D elements view perspective

| Property Value | Description |
| :--- | :--- |
| **number** | The distance of the element from the view, in pixels |
| **`none`** | Defaults. Same as `0`. No perspective |

## CSS Property: `perspective-origin`

CSS properties **`perspective-origin`** specifies the **X-axis** and **Y-axis** on which the 3D
element is based. This property allows you to change the bottom position of the 3D element.

| Property Value | Description |
| :--- | :--- |
| **x-position** | Specify the **abscissa** of the vanishing point |
| **y-position** | Specify the **ordinate** of the vanishing point |

## CSS Property: `backface-visibility`

CSS property **`backface-visibility`** specifies whether the element **is visible when the back of
the element faces the viewer**.

The back of the element is **a mirror image of its front**. Although not visible in 2D, the back can
become visible when the transformation causes the element to rotate in 3D space. (This property has
no effect on the 2D transformation, it has no perspective.)

| Property Value | Description |
| :--- | :--- |
| **`visible`** | When the back is facing the user **visible** |
| **`hidden`** | When the back is facing the user **not visible** |

## CSS Property: `translate`

CSS properties **`translate`** allow you to specify translations in *`transforms`* separately and
independently of the *`transform`* properties. This better reflects typical user interface usage and
saves the exact order of conversion functions that must be remembered when specifying a transform value.

!!! warn "Note"
    Currently only Firefox supports this property

| Property Value | Description |
| :--- | :--- |
| **`none`** | Indicates that the panning effect is not applied |
| A length / percent value | A length value or percentage **indicates that X axis** and **Y axis** use the same value for **translation in two dimensions**. Equivalent to `translate()` (2D translation) function specifying a single value |
| Two length / percent values | The two length values or percentages indicate the translation in **two-dimensional** according to the specified values of **X-axis** and **Y-axis**. Equivalent to `translate()` (2D translation) function specifying two values |
| Three length / percent values | The three length values or percentages indicate the translation in **three-dimensional** according to the specified values of **X-axis**, **Y-axis**, **Z-axis**. Equivalent to `translate3d()` (3D translation) function |

## Example

```css
.showbf div {
  backface-visibility: visible; /* Specify the back orientation to be visible */
}

.container {
  width: 150px;
  height: 150px;
  margin: 75px 0 0 75px;
  border: none;
}

.cube {
  width: 100%;
  height: 100%;
  perspective: 550px; /* Specify the perspective effect as 550px */
  perspective-origin: 150% 150%; /* Specify the X-axis and Y-axis positions of the observation at 150% each */
  transform-style: preserve-3d; /* Specifies that child elements are in 3D space */
}

.face {
  display: block;
  position: absolute;
  width: 100px;
  height: 100px;
  border: none;
  line-height: 100px;
  font-family: sans-serif;
  font-size: 60px;
  color: white;
  text-align: center;
}

.front {
  background: rgba(0, 0, 0, 0.3);
  transform: translateZ(50px); /* Define 3D transformation, Z axis is 50px */
}

.back {
  background: rgba(0, 255, 0, 1);
  color: black;
  transform: rotateY(180deg) translateZ(50px); /* Define a 3D transformation with 180 degrees on the Y axis and 50px on the Z axis */
}

.right {
  background: rgba(196, 0, 0, 0.7);
  transform: rotateY(90deg) translateZ(50px); /* Define a 3D transformation with 90 degrees on the Y axis and 50px on the Z axis */
}

.left {
  background: rgba(0, 0, 196, 0.7);
  transform: rotateY(-90deg) translateZ(50px); /* Define 3D transformation, Y-axis is -90 degrees, Z-axis is 50px */
}

.top {
  background: rgba(196, 196, 0, 0.7);
  transform: rotateX(90deg) translateZ(50px); /* Define 3D transformation, X-axis is 90 degrees, Z-axis is 50px */
}

.bottom {
  background: rgba(196, 0, 196, 0.7);
  transform: rotateX(-90deg) translateZ(50px); /* Define 3D transformation, X-axis is -90 degrees, Z-axis is 50px */
}
```

```html
<div class="container">
  <div class="cube showbf">
    <div class="face front">1</div>
    <div class="face back">2</div>
    <div class="face right">3</div>
    <div class="face left">4</div>
    <div class="face top">5</div>
    <div class="face bottom">6</div>
  </div>
</div>
```

### Example: Use `translate` Property

```css
div {
  width: 150px;
  margin: 0 auto;
  background:#ff0;
}

p {
  padding: 10px 5px;
  border: 3px solid black;
  border-radius: 20px;
  font-size: 1.2rem;
  text-align: center;
}

.translate {
  transition: translate 1s;
}

div:hover .translate {
  translate: 200px 50px;
}
```

```html
<div>
  <p class="translate">Translation</p>
</div>
```

TOPICS: outline property
        outline-style property
        outline-width property
        outline-color property

# CSS Property: `outline`

The CSS **`outline`** property is used to set **one** or **multiple individual outlines** shorthand
propertys, such as **`outline-style`**, **`outline-width`** and **`outline-color`**. In most cases,
shorthand propertys are more desirable and convenient.

The outline and frame are different in the following aspects:

- The outlines do not occupy space, they are drawn on the content.
- The outline may be non-rectangular. In Gecko/Firefox, the outline is rectangular, but Opera will
- draw non-rectangular shapes around the element structure.

## CSS Property: `outline-style`

The CSS **`outline-style`** property is used to set the **outline style of an element**.

The outline of an element is a line drawn around the element, located on the periphery of the border,
making the element stand out.

Most of the time it is more convenient to use the shorthand property **`outline`** instead of
**`outline-style`**, **`outline-width`** and **`outline-color`**.

| Property value | Description |
| :--- | :--- |
| **`none`** | Default. Define **no contour**. |
| **`dotted`** | Define the **point outline**. |
| **`dashed`** | Define **dashed outline**. |
| **`solid`** | Define **solid outline**. |
| **`double`** | Define **Double-line contour**. The width of the double line is equal to the value of **`outline-width`**. |
| **`groove`** | Define the 3D groove profile. This effect depends on the **`outline-color`** value. |
| **`ridge`** | Define the 3D convex contour. This effect depends on the **`outline-color`** value. |
| **`inset`** | Define 3D concave contour. This effect depends on the **`outline-color`** value. |
| **`outset`** | Define 3D convex contours. This effect depends on the **`outline-color`** value. |
| **`inherit`** | Specifies that the outline style settings should be inherited from the parent element. |

## CSS Property: `outline-width`

The CSS **`outline-width`** property is used to set the width of an element’s **outline**. The
outline of an element is a line drawn around the element, located on the periphery of **`border`**.

!!! warn "Note"
    Always declare the **`outline-style`** property before the **`outline-width`** property. An
    element can only change the width of its outline after it gets an outline.

| Property value | Description |
| :--- | :--- |
| **`thin`** | Requires **thin outline**. |
| **`medium`** | Default. Specifies **medium profile**. |
| **`thick`** | Prescribe **thick outline**. |
| **length** | Allows you to specify the value of **Outline thickness**. |
| **`inherit`** | Specifies that the outline width setting should be inherited from the parent element. |

## CSS Property: `outline-color`

The CSS **`outline-color`** property is used to set the color of an element’s outline.

| Property value | Description |
| :--- | :--- |
| **color** | Specify the outline color. Find a complete list of color values in [**CSS color values**](/en/webfrontend/CSS_color). |
| **`invert`** | default. Perform color inversion (reverse color). Make the outline visible in different background colors. |
| **`inherit`** | Specifies that the outline color setting should be inherited from the parent element. |

## Shorthand example

```css
/* Two identical statements */
:link:hover { outline: 1px solid #000; }
:link:hover { outline: solid black 1px; }
```

## Use the `outline-color` property

```html
<p>My outline is blue, as you can see.</p>
```

```css
p {
  outline: 2px solid;      /* Set outline width and style */
  outline-color: #0000FF;  /* Draw the outline in blue */
  margin: 5px;
}
```

## Use the `outline-width` property

```css
span {
  outline-style: solid;
  display: inline-block;
  margin: 20px;
}

#thin {
  outline-width: thin;
}

#medium {
  outline-width: medium;
}

#thick {
  outline-width: thick;
}

#twopixels {
  outline-width: 2px;
}

#oneex {
  outline-width: 1ex;
}

#em {
  outline-width: 1.2em;
}
```

```html
<span id="thin">thin</span>
<span id="medium">medium</span>
<span id="thick">thick</span>
<span id="twopixels">2px</span>
<span id="oneex">1ex</span>
<span id="em">1.2em</span>
```

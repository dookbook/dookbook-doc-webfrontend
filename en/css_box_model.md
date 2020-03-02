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

# CSS Box Model

**CSS box model** is essentially a box that encapsulates surrounding HTML elements. It includes:
**margin**, **border**, **fill**, and **actual content**.

The box model allows us to place elements in the space between other elements and
surrounding element borders

The following picture illustrates the Box Model:

![CSS Box Model](/media/webfrontend__css-box-model.png)

Explanation of different parts:

- **Margin** -Clear the border area. Margin has no background color, it is completely transparent
- **Border** -The padding and content around the border. The border is affected by the background
color of the box
- **Padding** -Clear the area around the content. Will be affected by the background color of the
box fill
- **Content** -The content of the box, displaying text and images

In order to set the width and height of the element correctly in all browsers, you need to know
how the box model works.

For example: When you specify the width and height properties of a CSS element, you just set the
width and height of the content area. To know that for full-size elements, you must also add padding,
borders, and margins.

In the example below, the actual width of the element is 280px, and the actual size is 300px.

```css
div {
  width:250px;
  padding:10px;
  border:5px solid gray;
  margin:10px;
}
```

## The actual size of the box is

- width = content.width + padding.left + padding.right + border.left + border.right

- height = content.height + padding.top + padding.bottom + border.top + border.bottom

## And the size the box needs to be

- width = content.width + padding.left + padding.right + border.left + border.right + margin.left + margin.right

- height = content.height + padding.top + padding.bottom + border.top + border.bottom + margin.top +
margin.bottom

# CSS box model property list

| Attributes | Description |
| :--- | :--- |
| **`margin`** | Margins for all four (**up**, **down**, **left** and **right**) elements. This is shorthand for the four margin properties. Can be negative |
| **`margin-top`** | Element's **top margin** |
| **`margin-right`** | Element's **right margin** |
| **`margin-bottom`** | Element's **bottom margin** |
| **`margin-left`** | Element's **left margin** |
| **`padding`** | The padding of all four (**up**, **down**, **left** and **right**) elements. The padding area refers to one **the content of the element** and **the space between its boundaries**. This attribute **cannot be negative** |
| **`padding-top`** | Element's **top padding** |
| **`padding-right`** | Element's **right padding** |
| **`padding-bottom`** | Element's **bottom padding** |
| **`padding-left`** | Element's **left padding** |
| **`border`** | Set shorthand properties for various **separate boundaries** |
| **`border-width`** | Set the **border width** of the box model |
| **`border-style`** | Used to set all element border styles |
| **`border-color`** | Is one for setting elements **four border colors** |
| **`border-top`** | The **above border** describing an element is an abbreviation of the three attributes `border-top-color`, `border-top-style`, and `border-top-width` |
| **`border-right`** | An element's **right border** is an abbreviation of three attributes: `border-right-color`, `border-right-style`, and `border-right-width` |
| **`border-bottom`** | Describes the element's **bottom border style**, which is an abbreviation of the three attributes of `border-bottom-color`, `border-bottom-style`, and `border-bottom-width` |
| **`border-left`** | The **left border** describing an element is an abbreviation of three attributes: `border-left-color`, `border-left-style`, and `border-left-width` |

## `margin` and `padding` Attribute value

Accept 1 ~ 4 optional parameters, each parameter takes the following values:

- When **one** value is specified, it applies the same margin to **all four sides**.
- When **two** values are specified, the first margin applies to the **top and bottom**, the second
to the **left and right**.
- When **three** values are specified, the first margin applies to the **top**, the second to the
**right and left**, the third to the **bottom**.
- When **four** values are specified, the margins apply to the **top**, **right**, **bottom**, and
**left** in that order (clockwise).

### Common Attribute Value

| Attribute Value | Description |
| :--- | :--- |
| length | Specify a fixed fill value. |
| **`%`** | Percentage based on parent element value.|

!!! warn "Difference between `margin` and `padding` property values"
    The **length** and **`%`** properties of **`margin`** can be negative; the **length** and **`%`**
    of **`padding`** cannot be negative.

### `margin` Attribute value

| Attribute Value | Description |
| :--- | :--- |
| **`auto`** | The browser will automatically select a suitable `margin` to apply. It can be used to center a block. |

## `border` Attribute value

| Attribute Value | Description |
| :--- | :--- |
| *border-width* | Specify the **width of the border** |
| *border-style* | Specify the border's **style** |
| *border-color* | Specify the **color of the border** |
| **`inherit`** | Specifies that the `border` attribute value should be inherited from the parent element |

### `border-width` Attribute value

| Attribute Value | Description |
| :--- | :--- |
| **`thin`** | **Thin border** |
| **`medium`** | Default. **Medium border** |
| **`thick`** | **Thick border** |
| length | **Custom** border width |
| **`inherit`** | Specifies that the border width should be inherited from the parent element |

### `border-style` Attribute value

| Attribute Value | Description |
| :--- | :--- |
| **`none`** | Define borderless |
| **`hidden`** | Same as **`none`**. Except when applied to tables, for tables, `hidden` is used to resolve border conflicts. |
| **`dotted`** | **Dotted border** |
| **`dashed`** | **Dotted line** |
| **`solid`** | **Solid line** |
| **`double`** | **Double line** |
| **`groove`** | Show as **sculpted border** |
| **`ridge`** | Show as **embossed border** |
| **`inset`** | Show as **immersed border** |
| **`outset`** | Show as **highlighting border** |
| **`inherit`** | Specifies that the border style should be inherited from the parent element |

### `border-color` Attribute value

| Attribute Value | Description |
| :--- | :--- |
| color | Border color, find full list of color values in [CSS color](/en/webfrontend/css_color) |
| **`transparent`** | The color of the specified border is **transparent**. This is the default |
| **`inherit`** | Inherit from parent element |

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
}

div p.a {
  background: red;
  padding: 10px 20px 5px 30px; /* Define padding 10px above, 20px right, 5px down, 30px left */
  margin-bottom: 20px; /* Define the margin at 20px*/
}

div p.b {
  background: red;
  padding: 10px 20px 5px; /* Define the padding to be 10px on the top, 20px on the left and 5px on the bottom */
}
```

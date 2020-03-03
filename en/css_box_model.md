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

| Attributes | Description |
| :--: | :--- |
| **`margin`** | Shorthand for the four direction (**up/top**, **down/bottom**, **left** and **right**) margin properties. Can be negative value. |
| **`margin-top`** | Element's **top margin** |
| **`margin-right`** | Element's **right margin** |
| **`margin-bottom`** | Element's **bottom margin** |
| **`margin-left`** | Element's **left margin** |

### Padding Properties

| Attributes | Description |
| :--: | :--- |
| **`padding`** | Shorthand for the four direction (**up/top**, **down/bottom**, **left** and **right**) padding properties. This attribute **cannot be negative**. |
| **`padding-top`** | Element's **top padding** |
| **`padding-right`** | Element's **right padding** |
| **`padding-bottom`** | Element's **bottom padding** |
| **`padding-left`** | Element's **left padding** |

### Attribute Values of `margin` and `padding`

They both have attribute values as follows:

| Attribute Value | Description |
| :--- | :--- |
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
/* margin-top: 10px, margin-right: 5px, margin-bottom: 15px, margin-left: 20px */
margin: 10px 5px 15px 20px;
```

```css
/* 3 parameters: top left-right bottom */
/* margin-top: 10px, margin-left=margin-right: 5px, margin-bottom: 15px */
margin: 10px 5px 15px;
```

```css
/* 2 parameters: top-bottom left-right */
/* margin-top=margin-bottom: 10px, margin-left=margin-right: 5px */
margin: 10px 5px;
```

```css
/* 1 parameter: top=bottom=left=right */
/* margins of top, bottom, left and right are all 10px */
margin: 10px;
```

## Border Properties

| Attributes | Description |
| :--: | :--- |
| **`border`** | Set shorthand properties for various **separate boundaries** |
| **`border-width`** | Set the **border width** of the box model |
| **`border-style`** | Used to set all element border styles |
| **`border-color`** | Is one for setting elements **four border colors** |
| **`border-top`** | The **above border** describing an element is an abbreviation of the three attributes `border-top-color`, `border-top-style`, and `border-top-width` |
| **`border-right`** | An element's **right border** is an abbreviation of three attributes: `border-right-color`, `border-right-style`, and `border-right-width` |
| **`border-bottom`** | Describes the element's **bottom border style**, which is an abbreviation of the three attributes of `border-bottom-color`, `border-bottom-style`, and `border-bottom-width` |
| **`border-left`** | The **left border** describing an element is an abbreviation of three attributes: `border-left-color`, `border-left-style`, and `border-left-width` |

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

## References

- [W3C CSS 2.2 Specification - Box Model](https://www.w3.org/TR/CSS22/box.html)

TOPICS: CSS Dimension
        width property
        min-width property
        max-width property
        height property
        min-height property
        max-height property

# CSS Dimension

The **CSS Dimension** property allows you to control the **height** and **width** of an element.

| Property | Description |
| :--- | :--- |
| **`width`**| sets **an element's width**. By default, it sets the width of the content area, but if **`box-sizing`** is set to **`border-box`**, it sets **the width of the border area**. |
| **`min-width`** | sets **the minimum width of an element**. It prevents the used value of the *`width`* property from becoming smaller than the value specified for `min-width`. |
| **`max-width`** | sets **the maximum width of an element**. It prevents the used value of the [**`width`**](/en/webfrontend/width) property from becoming larger than the value specified by `max-width`. |
| **`height`** | sets **height of an element**. By default, the property defines the **height of the content area**. If **`box-sizing`** is set to **`border-box`**, however, it instead determines **the height of the border area**. |
| **`min-height`** | sets **the minimum height of an element**. It prevents the used value of the **`height`** property from becoming smaller than the value specified for `min-height`. |
| **`max-height`** | sets **the maximum height of an element**. It prevents the used value of the **`height`** property from becoming larger than the value specified for `max-height`. |

## CSS Dimension Property Value

| Property Value | Description |
| :--- | :--- |
| length | Use **`px`**, **`rem`**, **`em`** and other units to define the width or height, See details[CSS length unit](/en/webfrontend/css_length_unit) |
| **`%`** | Percentage based on **parent element** height or width |
| **`auto`** | Defaults. Browser calculates automatically |
| **`inherit`** | Inherited from parent element |

## Example

```html
<p id="a">This is a paragraph</p>
<p id="b">This is a paragraph</p>
<p id="c">This is a paragraphThis is a paragraphThis is a paragraphThis is a paragraphThis is a paragraphThis is a paragraphThis is a paragraphThis is a paragraph</p>
</div>
```

```css
/* Defines 100px width and height of the element */
#a { width: 100px; height: 100px; background: #0f0; }

/* Defines the minimum width and height of the element at 50px each */
#b { min-width: 50px; min-height: 50px; background: #00f; }

/* Defines the element's maximum width and height of 200px */
#c { max-width: 200px; max-height: 200px; background: #f00; }
```

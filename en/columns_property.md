TOPICS: columns property
        column-width property
        column-count property

# CSS Property: `columns`

The CSS **`columns`** property is used to set the **column width** and **column number** of the element.
Is the **shorthand property** of the **`column-width`** and **`column-count`** propertys. As with all
shorthand propertys, any omitted subvalues will be set to their initial values.

## CSS `column-width` Property

The CSS **column-width`** property suggests a **optimum column width**. The column width is the
maximum width of the column before adding another column.

| Property Value | Description |
| :--- | :--- |
| **`auto`** | The browser will determine the width of the column. |
| **length** | Specify the length of the column width. |

## CSS `column-count` Property

The CSS **`column-count`** property describes the **column number** of the element.

| Property Value | Description |
| :--- | :--- |
| **number** | The optimal number of columns prevents the contents of the elements from flowing out. |
| **`auto`** | The number of columns will depend on other property, for example: *`column-width`*. |

## Examples

```css
.newspaper {
  columns: 80px 2; /* The column width is 80px and the number of columns is 2 */
}
```

```html
<div class="newspaper">
Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.
Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla facilisi. Nam liber tempor cum soluta nobis eleifend option congue nihil imperdiet doming id quod mazim placerat facer possim assum. Typi non habent claritatem insitam; est usus legentis in iis qui facit eorum claritatem. Investigationes demonstraverunt lectores legere me lius quod ii legunt saepius.
</div>
```

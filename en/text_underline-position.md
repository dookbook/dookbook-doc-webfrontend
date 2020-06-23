TOPICS: text-underline-position property

# CSS Property: `text-underline-position`

When the value of the [**`text-decoration`**](/en/webfrontend/text-decoration_property) property is
set to *`underline`*, you can use the **`text-underline-position`** property Set
**underlined position** for it.

## Property value

| Property Value | Description |
| :--- | :--- |
| **`auto`** | The user agent will confirm whether the underscore is placed on or below the letter baseline according to its own algorithm. |
| **`under`** | The position of the underline is forced to be **below the baseline of the letters**. At this position, the underline will not pass through any letters, so as to ensure that the subscript of the mathematical equation or chemical formula is not blocked by the underline. |
| **`left`** | In **vertical typesetting mode**, make the underline position on the left side of the text**, in horizontal typesetting mode, it is the same as *`under`*. |
| **`right`** | In **vertical layout mode**, make the underline position on the **right side of the text**, in horizontal layout mode, it is the same as *`under`*. |

## Examples

Since the **`text-underline-position`** property can be inherited and cannot be reset with the
shorthand property [**`text-decoration`**](/en/webfrontend/text-decoration_property), it should be
The global level sets its value. For example, the *`under`* value is very useful for a document that
includes a lot of mathematical or chemical formulas using subscripts.

```css
:root {
  text-underline-position: under;
}
```

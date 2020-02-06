TOPICS: <hr>

# HTML Horizontal Rule Element: `<hr>`

The **HTML `<hr>` element** represents a **thematic break** between paragraph-level elements: for example,
a change of scene in a story, or a shift of TOPICS within a section.

Historically, this has been presented as a **horizontal rule or line**. While it may still be displayed
as a horizontal rule in visual browsers, this element is now defined in semantic terms, rather than
presentational terms, so if you wish to draw a horizontal line, you should do so using appropriate [[CSS]].

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*. |
| **Permitted content** | None, it is an *empty element*. |
| **Tag omission** | It must have start tag, but must not have an end tag. |
| **Permitted parents** | Any element that accepts *flow content*.|
| **Permitted ARIA roles** | `presentation` |
| **DOM interface** | **`HTMLHRElement`** |

## Attributes

This element's attributes include the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| ~~`align`~~ | (**Deprecated**, using CSS instead) Sets the **alignment** of the rule on the page. If no value is specified, the default value is `left`.
| ~~`color`~~ | (**Deprecated**, using CSS instead) Sets the **color** of the rule through *color name* or *hexadecimal value*.
| ~~`noshade`~~ | (**Deprecated**, using CSS instead) Sets the rule to have **no shading**.
| ~~`size`~~ | (**Deprecated**, using CSS instead) Sets the **height**, *in pixels*, of the rule.
| ~~`width`~~ | (**Deprecated**, using CSS instead) Sets the **length** of the rule on the page through a *pixel* or *percentage* value.

## Example

```html
<p>
  This is the first paragraph of text.
  This is the first paragraph of text.
  This is the first paragraph of text.
  This is the first paragraph of text.
</p>

<hr>

<p>
  This is the second paragraph of text.
  This is the second paragraph of text.
  This is the second paragraph of text.
  This is the second paragraph of text.
</p>
```

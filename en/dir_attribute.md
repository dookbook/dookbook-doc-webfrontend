TOPICS: dir attribute

# HTML Global Attribute: `dir`

The **`dir`** [global attribute](/en/webfrontend/HTML_Global_Attributes) is an enumerated attribute
that indicates the directionality of the element's text.

## Attribute Value

| Value | Description |
| :-- | :-- |
| `ltr` | Default. Direction of text from left to right. |
| `rtl` | Text direction from right to left. |
| `auto` | Let the browser determine the text direction based on the content. Recommended only when text orientation is unknown. |

## Usage notes

- This attribute is mandatory for the [`<bdo>`](/en/webfrontend/<bdo>) element where it has a
different semantic meaning.
- This attribute is not inherited by the [`<bdi>`](/en/webfrontend/<bdo>) element. If not set, its
value is `auto`.
- This attribute can be overridden by the CSS properties *`direction`* and *`unicode-bidi`*, if a CSS
page is active and the element supports these properties.
- As the directionality of the text is semantically related to its content and not to its presentation,
it is recommended that web developers use this attribute instead of the related CSS properties when
possible. That way, the text will display correctly even on a browser that doesn't support CSS or has
the CSS deactivated.
- The `auto` value should be used for data with an unknown directionality, like data coming from user
input, eventually stored in a database.

## Example

```html
<bdo dir="rtl">Text direction from right to left!</bdo>
```

## See also

- [`HTMLElement.dir`](/en/webfrontend/HTMLElement.dir) that reflects this attribute.
- All HTML [global attributes](/en/webfrontend/HTML_Global_Attributes).

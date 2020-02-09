TOPICS: <wbr>

# HTML Word Break Opportunity Element: `<wbr>`

The **HTML `<wbr>` element** represents a **word break opportunity** — a position within text where the
browser may *optionally break a line*, though its line-breaking rules would not
otherwise create a break at that location.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*.|
| **Permitted content** | *Empty* |
| **Tag omission** | It is an **[empty element](/en/webfrontend/Empty_Element)**; it must have a start tag, but must not have an end tag. |
| **Permitted parents** | Any element that accepts *phrasing content*. |
| **Permitted ARIA roles** | Any |
| **DOM interface** | **`HTMLElement`** |

## Attributes

This element only includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

## Usage Notes

On *[[UTF-8]]* encoded pages, `<wbr>` behaves like the *`U+200B ZERO-WIDTH SPACE`* code point. In particular,
it behaves like a *Unicode bidi BN* code point, meaning *it has no effect on
bidi-ordering*: `<div dir="rtl">123,<wbr>456</div>` displays,
when not broken on two lines, `123,456` and not `456,123`.

For the same reason, the `<wbr>` element does not introduce a hyphen at the line break point.
To make a hyphen appear only at the end of a line,
use the **soft hyphen character entity** (**`&shy;`**) instead.

This element was first implemented in Internet Explorer 5.5 and was officially defined in HTML5.

## Example

The *Yahoo Style Guide* recommends breaking a URL before punctuation, to avoid leaving a
punctuation mark at the end of the line, which the reader might mistake for the end of the URL.

```html
<p>http://this<wbr>.is<wbr>.a<wbr>.really<wbr>.long<wbr>.example<wbr>.com/With<wbr>/deeper<wbr>/level<wbr>/pages<wbr>/deeper<wbr>/level<wbr>/pages<wbr>/deeper<wbr>/level<wbr>/pages<wbr>/deeper<wbr>/level<wbr>/pages<wbr>/deeper<wbr>/level<wbr>/pages</p>
```

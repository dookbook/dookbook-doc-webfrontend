TOPICS: <head>

# HTML Head Element: `<head>`

The HTML `<head>` element contains machine-readable information (**metadata**) about the document,
like its *title* ([`<title>`](/en/webfrontend/<title>)), *author*, *description*, links to
*scripts ([[JavaScript]])* ([`<script>`](/en/webfrontend/<script>)), and *style sheets ([[CSS]])*
([`<link>`](/en/webfrontend/<link>)) files that should be applied to the HTML.

!!! info
    **Note**: `<head>` primarily holds information for **machine processing**, not human-readability.
    For human-visible information, like top-level headings and listed authors, see the [`<header>`]
    (/en/webfrontend/<header>) element.

[[HTML]]5-compliant browsers automatically create a `<head>` element if its tags are omitted in the
markup. [This auto-creation is not guaranteed in ancient browsers](https://www.stevesouders.com/blog/2010/05/12/autohead-my-first-browserscope-user-test/).

## `<head>` Meta

|  |  |
| :-- | :-- |
| **Content categories** | None |
| **Permitted content** | If the document is an [`<iframe>`](/en/webfrontend/<iframe>) `srcdoc` document, or if title information is available from a higher level protocol (like the subject line in HTML email), zero or more elements of metadata content.<br><br>Otherwise, one or more elements of metadata content where exactly one is a [`<title>`](/en/webfrontend/<title>/) element.|
| **Tag omission** | The start tag may be omitted if the first thing inside the `<head>` element is an element. The end tag may be omitted if the first thing following the `<head>` element is not a space character or a comment. |
| **Permitted parents** | An [`<html>`](/en/webfrontend/<html>) element, as its first child.|
| **Permitted ARIA roles** | None|
| **DOM interface** | **`HTMLHeadElement`** |

## Example

```html
<html>
  <head>
    <title>文档标题</title>
  </head>
</html>
```

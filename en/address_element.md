TOPICS: <address>

# HTML Contact Element: `<address>`

The **HTML `<address>` element** indicates that the enclosed HTML provides **contact information** for
a person or people, or for an organization.

The contact information provided by an `<address>` element's contents can take whatever form is
appropriate for the context, and may include any type of contact information that is needed,
such as *physical address*, *[[URL]]*, *email address*, *phone number*, *social media handle*,
*geographic coordinates*, and so forth. The `<address>` element should include the name of the
person, people, or organization to which the contact information refers.

`<address>` can be used in a variety of contexts, such as providing a business's contact information
in the page header, or indicating the author of an article by including an `<address>`
element within the *[`<article>`](/en/webfrontend/<article>)*.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *palpable content*. |
| **Permitted content** | *Flow content*, but with no nested `<address>` element, no heading content ([`<hgroup>`](/en/webfrontend/<hgroup>), [`<h1>`](/en/webfrontend/<h1>), [`<h2>`](/en/webfrontend/<h2>), [`<h3>`](/en/webfrontend/<h3>), [`<h4>`](/en/webfrontend/<h4>), [`<h5>`](/en/webfrontend/<h5>), [`<h6>`](/en/webfrontend/<h6>)), no sectioning content ([`<article>`](/en/webfrontend/<article>), [`<aside>`](/en/webfrontend/<aside>), [`<section>`](/en/webfrontend/<section>), [`<nav>`](/en/webfrontend/<nav>)), and no [`<header>`](/en/webfrontend/<header>) or [`<footer>`](/en/webfrontend/<footer>) element. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *flow content*, but always excluding `<address>` elements (according to the logical principle of symmetry, if `<address>` tag, as a parent, can not have nested `<address>` element, then the same `<address>` content can not have `<address>` tag as its parent). |
| **Permitted ARIA roles** | None |
| **DOM interface** | **`HTMLElement`** |

## Attributes

This element only includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

## Usage Notes

- To represent an arbitrary address, one that is not related to the contact information, use a
[`<p>`](/en/webfrontend/<p>) element rather than the `<address>` element.
- This element should not contain more information than the contact information, like a publication
date (which belongs in a [`<time>`](/en/webfrontend/<time>) element).
- Typically an `<address>` element can be placed inside the
[`<footer>`](/en/webfrontend/<footer>) element of the current section, if any.

## Example

This example demonstrates the use of `<address>` to demarcate the contact
information for an article's author.

```html
<address>
    You can contact author at <a href="https://dookbook.info/about/en/">
    dookbook.info</a>.<br>
    If you see any bugs, please <a href="mailto:dookbook@zhiliaokeji.com">
    contact webmaster</a>.<br>
    You may also want to visit us:<br>
    Mozilla Foundation<br>
    331 E Evelyn Ave<br>
    Mountain View, CA 94041<br>
    USA
</address>
```

TOPICS: :lang()

# CSS Pseudo-Class: `:lang()`

The **`:lang()`** CSS pseudo-class matches elements based on the **language** they are determined
to be in.

!!! warn "Note"
    In HTML, the **language** is determined by a combination of the [`lang`](/en/webfrontend/lang_attribute)
    attribute, the [`<meta>`](/en/webfrontend/<meta>)
    element, and possibly by information from the protocol (such as HTTP headers). For other document
    types there may be other document methods for determining the **language**.

## Example

In this example, the `:lang()` pseudo-class is used to match the parents of quote elements ([`<q>`](/en/webfrontend/<`meta`>))
using child combinators. Note that this doesn't illustrate the only way to do this, and that the
best method to use depends on the type of document. Also note that Unicode values are used to
specify some of the special quote characters.

```html
<div lang="en"><q>This English quote has a <q>nested</q> quote inside.</q></div>
<div lang="fr"><q>This French quote has a <q>nested</q> quote inside.</q></div>
<div lang="de"><q>This German quote has a <q>nested</q> quote inside.</q></div>
```

```css
:lang(en) > q { quotes: '\201C' '\201D' '\2018' '\2019'; }
:lang(fr) > q { quotes: '« ' ' »'; }
:lang(de) > q { quotes: '»' '«' '\2039' '\203A'; }
```

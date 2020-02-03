TOPICS: <dl>
        <dt>
        <dd>

# HTML Description List Element: `<dl>`

The HTML `<dl>` element represents a **description list**. The element encloses a list of groups of
terms (specified using the `<dt>` element) and descriptions (provided by `<dd>` elements).
Common uses for this element are to implement a *glossary* or to display
*metadata* (a list of key-value pairs).

## `<dl>` Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, and if the `<dl>` element's children include one name-value group, *palpable content*.
| **Permitted content** | Either: Zero or more groups each consisting of one or more **`<dt>`** elements followed by one or more **`<dd>`** elements, optionally intermixed with **[`<script>`](/en/webfrontend/<script>)** and **[`<template>`](/en/webfrontend/<template>)** elements.<br><br>Or: One or more **[`<div>`](/en/webfrontend/<div>)** elements, optionally intermixed with **[`<script>`](/en/webfrontend/<script>)** and **[`<template>`](/en/webfrontend/<template>)** elements.
| **Tag omission** | None, both the starting and ending tag are mandatory.
| **Permitted parents** | Any element that accepts flow content.
| **Permitted ARIA roles** | `group`, `presentation` |
| **DOM interface** | **`HTMLDListElement`** |

## `<dl>` Attributes

This element only includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

## HTML Term Element: `<dt>`

The **HTML `<dt>` element** specifies a **term** in a description or definition list, and as such must
be used inside a *`<dl>`* element. It is usually followed by a *`<dd>`* element; however, multiple `<dt>`
elements in a row indicate several terms that are all defined by the immediate next `<dd>` element.

The subsequent `<dd>` (**Description Details**) element provides the definition or other related text
associated with the term specified using `<dt>`.

### `<dt>` Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | None. |
| **Permitted content** | *Flow content*, but with no *[`<header>`](/en/webfrontend/<header>)*, *[`<footer>`](/en/webfrontend/<footer>)*, sectioning content or heading content descendants. |
| **Tag omission** | Must have a start tag. The end tag may be omitted if this element is immediately followed by another `<dt>` element or a `<dd>`, or if there is no more content in the parent element. |
| **Permitted parents** | Before a `<dt>` or a `<dd>` element, inside a `<dl>` or (in `WHATWG` HTML) a [`<div>`](/en/webfrontend/<div>) that is inside a `<dl>`. |
| **Permitted ARIA roles** | None |
| **DOM interface** | **`HTMLDListElement`** |

## HTML Details Element: `<dd>`

The **HTML `<dd>` element** provides the **details** about or the **definition** of the preceding term
(`<dt>`) in a description list (`<dl>`).

### `<dd>` Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | None. |
| **Permitted content** | *Flow content*. |
| **Tag omission** | The start tag is required. The end tag may be omitted if the `<dd>` element is immediately followed by another `<dd>` element or a `<dt>` element, or if there is no more content in the parent element. |
| **Permitted parents** | **`<dl>`** or (in *[[WHATWG]]* HTML) a **[`<div>`](/en/webfrontend/<div>)** that is inside a `<dl>`. |
| **Previous sibling** | **`<dt>`** or another **`<dd>`** element.|
| **Permitted ARIA roles** | None |
| **DOM interface** | **`HTMLElement`** |

### `<dd>` Attributes

| Attribute | Description |
| :-- | :-- |
| `nowrap` (*no standard*) | If the value of this attribute is set to `yes`, the definition text will not wrap. The default value is `no`.

## Examples

### Single term and description

```html
<dl>
  <dt>Firefox</dt>
  <dd>
    A free, open source, cross-platform,
    graphical web browser developed by the
    Mozilla Corporation and hundreds of
    volunteers.
  </dd>

  <!-- Other terms and descriptions -->
</dl>
```

### Multiple terms, single description

```html
<dl>
  <dt>Firefox</dt>
  <dt>Mozilla Firefox</dt>
  <dt>Fx</dt>
  <dd>
    A free, open source, cross-platform,
    graphical web browser developed by the
    Mozilla Corporation and hundreds of
    volunteers.
  </dd>

  <!-- Other terms and descriptions -->
</dl>
```

### Single term, multiple descriptions

```html
<dl>
  <dt>Firefox</dt>
  <dd>
    A free, open source, cross-platform,
    graphical web browser developed by the
    Mozilla Corporation and hundreds of
    volunteers.
  </dd>
  <dd>
    The Red Panda also known as the Lesser
    Panda, Wah, Bear Cat or Firefox, is a
    mostly herbivorous mammal, slightly larger
    than a domestic cat (60 cm long).
  </dd>

  <!-- Other terms and descriptions -->
</dl>
```

### Multiple terms and descriptions

It is also possible to define multiple terms with multiple corresponding descriptions,
by combining the examples above.

### Metadata

Description lists are useful for displaying metadata as a list of key-value pairs.

```html
<dl>
  <dt>Name</dt>
  <dd>Godzilla</dd>
  <dt>Born</dt>
  <dd>1952</dd>
  <dt>Birthplace</dt>
  <dd>Japan</dd>
  <dt>Color</dt>
  <dd>Green</dd>
</dl>
```

Tip: It can be handy to define a key-value separator in the CSS, such as:

```css
dt::after {
  content: ": ";
}
```

### Wrapping name-value groups in `<div>` elements

[[WHATWG]] HTML allows wrapping each name-value group in a `<dl>` element in a
[`<div>`](/en/webfrontend/<div>) element.
This can be useful when using microdata, or when [global attributes](/en/webfrontend/HTML_Global_Attributes)
apply to a whole group, or for styling purposes.

```html
<dl>
  <div>
    <dt>Name</dt>
    <dd>Godzilla</dd>
  </div>
  <div>
    <dt>Born</dt>
    <dd>1952</dd>
  </div>
  <div>
    <dt>Birthplace</dt>
    <dd>Japan</dd>
  </div>
  <div>
    <dt>Color</dt>
    <dd>Green</dd>
  </div>
</dl>
```

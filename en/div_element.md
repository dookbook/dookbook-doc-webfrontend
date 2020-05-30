TOPICS: <div>

# HTML Content Division Element: `<div>`

The **HTML Content Division element** (**`<div>`**) is the generic container for *flow content*.
It has no effect on the content or layout until styled using [[CSS]].

As a "pure" container, the `<div>` element does not inherently represent anything. Instead, it's
used to group content so it can be easily styled using the *`class`* or *`id`* attributes, marking a
section of a document as being written in a different language (using the `lang` attribute), and so on.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *palpable content*.|
| **Permitted content** | *Flow content*. <br>Or (in *[[WHATWG]]* HTML): If the parent is a **[`<dl>`](/en/webfrontend/<dl>)** element: one or more **[`<dt>`](/en/webfrontend/<dt>)** elements followed by one or more **[`<dd>`](/en/webfrontend/<dd>)** elements, optionally intermixed with *[`<script>`](/en/webfrontend/<script>)* and *[`<template>`](/en/webfrontend/<template>)* elements. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *flow content*.<br>Or (in *[[WHATWG]]* HTML): **[`<dl>`](/en/webfrontend/<dl>)** element. |
| **Permitted ARIA roles** | Any |
| **DOM interface** | **`HTMLDivElement`** |

## Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

!!! warn "The `align` Attribute Obsoleted"
    The `align` attribute is obsolete; do not use it anymore. Instead, you should use CSS properties
    or techniques such as CSS Grid or CSS Flexbox to align and position `<div>` elements on the page.

## Usage Notes

The `<div>` element should be used only when no other semantic element (such as
*[`<article>`](/en/webfrontend/<article>)* or *[`<nav>`](/en/webfrontend/<nav>)*) is appropriate.

## Examples

### A Simple Example

```html
<div>
  <p>Any kind of content here. Such as
  &lt;p&gt;, &lt;table&gt;. You name it!</p>
</div>
```

### A Styled Example

This example creates a shadowed box by applying a style to the `<div>` using CSS. Note the use of
the `class` attribute on the `<div>` to apply the style named `"shadowbox"` to the element.

```html
<div class="shadowbox">
  <p>Here's a very interesting note displayed in a
  lovely shadowed box.</p>
</div>
```

```css
.shadowbox {
  width: 15em;
  border: 1px solid #333;
  box-shadow: 8px 8px 5px #444;
  padding: 8px 12px;
  background-image: linear-gradient(180deg, #fff, #ddd 40%, #ccc);
}
```

## Browser compatibility

| - | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
| `<div>`  | support | support | support |

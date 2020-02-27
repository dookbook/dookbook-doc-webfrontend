TOPICS: style attribute

# HTML Global Attribute: `style`

The **`style`** [global attribute](/en/webfrontend/HTML_Global_Attributes) contains **CSS styling
declarations to be applied to the element**. Note that it is recommended for styles to be defined in
a separate file or files. This attribute and the [*`<style>`*](/en/webfrontend/<style>) element have
mainly the purpose of allowing for quick styling, for example for testing purposes.

!!! warn "Usage note"
    This attribute must not be used to convey semantic information. Even if all styling
    is removed, a page should remain semantically correct. Typically it shouldn't be used to hide
    irrelevant information; this should be done using the [`hidden`](/en/webfrontend/hidden_attribute)
    attribute.

## Example

The following shows that the inline style of the `style` attribute overrides the style of the
[*`<style>`*](/en/webfrontend/<style>) tag.

```html
<style>
  h1 { color: red }
</style>

<h1 style="color:blue;text-align:center">这是一个标题</h1>
<p style="color:green">这是一个段落。</p>
```

## See also

- All HTML [global attributes](/en/webfrontend/HTML_Global_Attributes).

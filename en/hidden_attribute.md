TOPICS: hidden attribute

# HTML Global Attribute: `hidden`

The [global attribute](/en/webfrontend/HTML_Global_Attributes) **`hidden`** is used to hide the element.
The `hidden` property can be set so that the user can only see an element when certain conditions
are met (such as selecting the **checkbox**, etc.). You can then use JavaScript to remove the `hidden`
attribute and make the element visible.

`Hidden` elements shouldn't be linked from non-hidden elements, and elements that are descendants of
a `hidden` element are still active, which means that script elements can still execute and form elements
can still submit. Elements and scripts may, however, refer to elements that are `hidden` in other contexts.

For example, it would be incorrect to use the *`href`* attribute to link to a section marked with the
`hidden` attribute. If the content is not applicable or relevant, then there is no reason to link
to it.

!!! warn "Note"
    The *`display`* attribute of CSS can override elements that have the `hidden` attribute.
    For instance, elements styled *`display: flex`* will be displayed despite the
    `hidden` attribute's presence.

## Example

```html
<p hidden>This is a hidden paragraph.</p>
<p>This is a visible paragraph.</p>
```

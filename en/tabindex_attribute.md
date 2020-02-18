TOPICS: tabindex attribute

# HTML Global Attribute: `tabindex`

The **`tabindex`** [global attribute](/en/webfrontend/HTML_Global_Attributes) indicates that its
element can be focused, and where it participates in sequential keyboard navigation (usually with the
!!!Tab!!! key, hence the name).

It accepts an integer as a value, with different results depending on the integer's value:

- A **negative value** (usually `tabindex="-1"`) means that the element is not reachable via sequential
keyboard navigation, but could be focused with JavaScript or visually. It's mostly useful to create
accessible widgets with JavaScript. You can observe the Tabindex Accessibility example below to
clear confusion.
- A `tabindex` of **`0`** means that the element should be focusable in sequential keyboard navigation,
but its order is defined by the document's source order.
- A **positive value** means that the element should be focusable, And can be accessed by keyboard navigation;
Each time the user presses the !!!Tab!!! key, Its relative order is increased according to the value
of **`tabindex`** and the focus is delayed. Most platforms provide a reverse-tab feature, typically
using the combination of !!!Shift!!! + !!!Tab!!!, which reverses the tabbing order. If multiple elements
have the same **`tabindex`**, their relative order is determined by their order in the current DOM.

If you set the `tabindex` attribute on a [`<div>`](/en/webfrontend/<div>), then its child content
cannot be scrolled with the arrow keys unless you set `tabindex` on the content.

!!! warn "Note"
    The maximum value of `tabindex` should not exceed **32767**. If not specified,
    its default value is `-1`.

## Example

```html
<a href="https://dookbook.info/" tabindex="2">DookBook</a><br/>
<a href="https://github.com/" tabindex="1">GitHub</a><br/>
<a href="http://www.google.com/" tabindex="3">Google</a>
<!--
    Click to 1, press Tab, and jump to 2 and 3
    Click 3 to jump to somewhere else
    Click 2 to jump to 3

    Tabindex jumps from small to large. If you click directly on the option with the largest tabindex ordinal in the module, jump to somewhere else, or not.
-->
<p><b>注释：</b>请尝试使用键盘上的 "Tab" 键在链接之间进行导航。</p>
```

## See also

- All HTML [global attributes](/en/webfrontend/HTML_Global_Attributes).
- [`HTMLElement.tabIndex`](/en/webfrontend/HTMLElement.tabIndex) that reflects this attribute
- Accessibility problems with `tabindex`: see [Don’t Use Tabindex Greater than 0](http://adrianroselli.com/2014/11/dont-use-tabindex-greater-than-0.html)
by Adrian Roselli

TOPICS: <button>
        <button> type attribute
        <button> name attribute
        <button> value attribute
        <button> autofocus attribute
        <button> form attribute
        <button> formaction attribute
        <button> formmethod attribute
        <button> formenctype attribute
        <button> formnovalidate attribute

# `<button>`

The **HTML `<button>` element** represents a **clickable button**, which can be used in forms or anywhere
in a document that needs simple, standard button functionality.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*, *Interactive content*, *listed, labelable, and submittable form-associated element*, *palpable content*. |
| **Permitted content** | *Phrasing content* but there must be no Interactive content. |
| **Tag omission** | None, both the starting and ending tag are mandatory.|
| **Permitted parents** | Any element that accepts *phrasing content*. |
| **Permitted ARIA roles** | `checkbox`, `link`, `menuitem`, `menuitemcheckbox`, `menuitemradio`, `radio`, `switch`, `tab` |
| **DOM interface** | **`HTMLButtonElement`** |

## Attributes

This element's attributes include the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| **`type`** | The **type of the button**. Possible values are:<br>**`submit`**:  (*default*) The button submits the form data to the server.<br>**`reset`**: The button resets all the controls to their initial values.<br>**`button`**: The button has no default behavior. It can have client-side scripts associated with the element's events, which are triggered when the events occur. |
| **`disabled`** |This *Boolean* attribute indicates that the user **cannot** interact with the button. If this attribute is not specified, the button inherits its setting from the containing element; if there is no containing element with the **`disabled`** attribute set, then the button is enabled. |
| **`name`** | The **name of the button**, which is submitted with the form data. |
| **`value`** | The **initial value** of the button. It defines the value associated with the button which is submitted with the form data. This value is passed to the server in params when the form is submitted. |
| **`autofocus`** | This *Boolean* attribute lets you specify that the button should have input **focus** when the page loads, unless the user overrides it. **Only one** form-associated element in a document can have this attribute specified. |
| `form` | The *[`<form>`](/en/webfrontend/<form>)* element that the button is associated with (its form owner). The value of the attribute must be the **`id`** attribute of a `<form>` element in the same document. This attribute enables you to associate this element to `<form>` anywhere within a document, not just as descendants of `<form>` elements. |
| `formaction` | Override the **`action`** attribute of the button's *[`<form>`](/en/webfrontend/<form>)* owner. |
| `formmethod` | Override the **`method`** attribute of the button's *[`<form>`](/en/webfrontend/<form>)* owner. |
| `formenctype` | Override the **`enctype`** attribute of the button's *[`<form>`](/en/webfrontend/<form>)* owner. |
| `formnovalidate` | Override the **`novalidate`** attribute of the button's *[`<form>`](/en/webfrontend/<form>)* owner. |
| `formtarget` | Override the **`target`** attribute of the button's *[`<form>`](/en/webfrontend/<form>)* owner. |

## Notes

`<button>` elements are much easier to style than *[`<input>`](/en/webfrontend/<input>)* elements.
You can add inner HTML content (think *[`<em>`](/en/webfrontend/<em>)*, *[`<strong>`](/en/webfrontend/<strong>)*
or even *[`<img>`](/en/webfrontend/<img>)*), and make use of*`::after`*and*`::before`* pseudo-element
to achieve complex rendering while [`<input>`](/en/webfrontend/<input>) only accepts a text value attribute.

If your buttons are not to submit form data to a server, be sure to set their `type` attribute to **`button`**.
Otherwise they will try to submit form data and to load the (nonexistent) response, possibly
destroying the current state of the document.

## Simple Example

```html
<button type="button" value="2">Click me</button>
<script>
  document.querySelector('button').onclick = function(e) {
    alert(this.value)
  }
</script>
```

## Accessibility Concerns

### Icon Buttons

Buttons that only use an icon to represent functionality do not have an accessible name. Accessible
names provide a programmatic hook for assistive technology such as screen readers to access when
they parse the document and generate an accessibility tree. Assistive technology then uses the
accessibility tree to navigate and manipulate page content.

To give an icon button an accessible name, supply a string of text for the `<button>` element that
concisely describes the button's functionality.

For example,

```html
<button name="favorite" type="button">
  <svg aria-hidden="true" viewBox="0 0 10 10"><path d="M7 9L5 8 3 9V6L1 4h3l1-3 1 3h3L7 6z"/></svg>
  Add to favorites
</button>
```

It is worth noting that leaving the button text visually apparent can aid people who may not
be familiar with the icon's meaning or understand the button's purpose. This is especially relevant
for people who are not as technologically sophisticated, or who may have different cultural
interpretations for the imagery the icon button uses.

### Size and Proximity

#### Size

Interactive elements such as buttons should provide an area large enough that it is easy to activate
them. This helps a variety of people, including people with motor control issues and people using
non-precise forms of input such as a stylus or fingers. A minimum interactive size of **44 by 44**
[CSS pixels](https://www.w3.org/TR/WCAG21/#dfn-css-pixels) is recommended.

#### Proximity

Large amounts of interactive content—including buttons—placed in close visual proximity to each other
should have space inserted to separate them. This spacing is beneficial for people who are
experiencing motor control issues, who may accidentally activate the wrong interactive content.

Spacing may be created using CSS properties such as `margin`.
See [Hand tremors and the giant-button-problem - Axess Lab](https://axesslab.com/hand-tremors/)

### Clicking and Focus

Whether clicking on a `<button>` causes it to (by default) become focused varies by browser and OS.
The results for [`<input>`](/en/webfrontend/<input>) of `type="button"` and `type="submit"` were
the same.

#### Does clicking on a `<button>` give it the focus

| Desktop Browsers | Windows 8.1 | OS X 10+ |
| :-- | :-- | :-- |
| Firefox 63+ | Yes | No (even with a `tabindex`) |
| Chrome 65+ | Yes | Yes |
| Safari 12+ | N/A | No (even with a `tabindex`) |

#### Does tapping on a `<button>` give it the focus

| Mobile Browsers | iOS 7.1+ | Android 4.4+ |
| :-- | :-- | :-- |
| Safari Mobile | No (even with a `tabindex`) | N/A |
| Chrome 35+ | No (even with a `tabindex`) | Yes |

## Browser compatibility

| - | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
| `<button>`  | support | support | support |

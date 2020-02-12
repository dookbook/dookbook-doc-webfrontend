TOPICS: <select>
        <option>
        <optgroup>
        <select> name attribute
        <select> multiple attribute
        <select> required attribute
        <select> disabled attribute
        <select> size attribute
        <select> autocomplete attribute
        <select> autofocus attribute
        <select> form attribute
        <option> value attribute
        <option> selected attribute
        <option> disabled attribute
        <option> label attribute
        <optgroup> label attribute
        <optgroup> disabled attribute
        <datalist>

# HTML Selection List: `<select>`/`<option>`/`<optgroup>`/`<datalist>`

The **HTML `<select>` element** represents **a control that provides a menu of options**.

The **HTML `<option`> element** is used to define an item contained in a *`<select>`*, an *`<optgroup>`*,
or a [`<datalist>`](/en/webfrontend/<datalist>) element. As such, `<option>` can represent menu items
in popups and other lists of items in an HTML document.

The **HTML `<optgroup>` element** creates a grouping of options (*`<option>`*) within a `<select>` element.

The **HTML `<datalist>` element** contains a set of *`<option>`* elements
that represent the values available for other controls.

## Technical Summary

| - | `<select>` | `<option>` | `<optgroup>` | `<datalist>` |
| :-- | :-- | :-- | :-- | :-- |
| **Content categories** | *flow content*, *phrasing content*, *interactive content*, *listed, labelable, resettable, and submittable form-associated element*. | None. | None. | *Flow content*, *phrasing content*. |
| **Permitted content** | Zero or more *`<option>`* or *`<optgroup>`* elements. | *Text*, possibly with escaped characters (like *`&eacute;`*). | Zero or more *`<option>`* elements. | Either *phrasing content*, or zero or more *`<option>`* elements. |
| **Tag omission** | None, both the starting and ending tag are mandatory. | The start tag is mandatory. The end tag is optional if this element is immediately followed by another *`<option>`* element or an *`<optgroup>`*, or if the parent element has no more content. | The start tag is mandatory. The end tag is optional if this element is immediately followed by another *`<optgroup>`* element, or if the parent element has no more content. | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | any element that accepts *phrasing content*. | A *`<select>`*, an *`<optgroup>`* or a *[`<datalist>`](/en/webfrontend/<datalist>)* element. | A *`<select>`* element. | Any element that accepts *phrasing content*. |
| **Permitted ARIA roles** | `menu` | None | None | None |
| **DOM interface** | **`HTMLSelectElement`** | **`HTMLOptionElement`** | **`HTMLOptGroupElement`** | **`HTMLDataListElement`** |

## `<select>` Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| **`name`** | This attribute is used to specify the **name** of the control. |
| **`multiple`** | This *Boolean* attribute indicates that **multiple options** can be selected in the list. If it is not specified, then only one option can be selected at a time. When `multiple` is specified, most browsers will show a scrolling list box instead of a single line dropdown. |
| **`required`** | A *Boolean* attribute indicating that an option with a non-empty string value must be selected. |
| **`disabled`** | This *Boolean* attribute indicates that the user cannot interact with the control. If this attribute is not specified, the control inherits its setting from the containing element, for example `<fieldset>`; if there is no containing element with the `disabled` attribute set, then the control is enabled. |
| **`size`** | If the control is presented as a scrolling list box (e.g. when `multiple` is specified), this attribute represents the number of rows in the list that should be visible at one time. Browsers are not required to present a select element as a scrolled list box. The default value is *`1`* according to the HTML5 specification. |
| **`autocomplete`** | A `DOMString` providing a hint for a user agent's autocomplete feature. |
| **`autofocus`** | This *Boolean* attribute lets you specify that a form control should have input focus when the page loads. Only one form element in a document can have the `autofocus` attribute. |
| **`form`** | This attribute lets you specify the *[`<form>`](/en/webfrontend/<form>)* element to which the `<select>` element is associated (that is, its "form owner"). If this attribute is specified, its value must be the same as the **`id`** of a [`<form>`](/en/webfrontend/<form>) element in the same document. This enables you to place `<select>` elements anywhere within a document, not just as descendants of their [`<form>`](/en/webfrontend/<form>) elements.

## `<option>` Attributes

| Attribute | Description |
| :-- | :-- |
| **`value`** | The content of this attribute represents the value to be submitted with the form, should this option be selected. If this attribute is omitted, the value is taken from the text content of the `<option>` element. |
| **`selected`** | If present, this *Boolean* attribute indicates that the option is *initially selected*. If the `<option>` element is the descendant of a `<select>` element whose *`multiple`* attribute is not set, only one single `<option>` of this `<select>` element may have the `selected` attribute. |
| **`disabled`** | If this *Boolean* attribute is set, this option is not checkable. Often browsers grey out such control and it won't receive any browsing event, like mouse clicks or focus-related ones. If this attribute is not set, the element can still be disabled if one of its ancestors is a disabled `<optgroup>` element. |
| `label` | This attribute is text for the label indicating the meaning of the option. If the `label` attribute isn't defined, its value is that of the element text content. |

## `<optgroup>` Attributes

| Attribute | Description |
| :-- | :-- |
| **`label`** | The name of the group of options, which the browser can use when labeling the options in the user interface. This attribute is mandatory if this element is used. |
| **`disabled`** | If this *Boolean* attribute is set, none of the items in this option group is selectable. Often browsers grey out such control and it won't receive any browsing events, like mouse clicks or focus-related ones. |

## `<datalist>` Attributes

This element has no other attributes than the [global attributes](/en/webfrontend/HTML_Global_Attributes),
common to all elements.

## Basic Usage of `<select>`

```html
<!-- The second value will be selected initially -->
<select name="choice">
  <option value="first">First Value</option>
  <option value="second" selected>Second Value</option>
  <option value="third">Third Value</option>
</select>
```

The above example shows typical **`<select>`** usage. It is given an `id` attribute to enable it to be
associated with a [`<label>`](/en/webfrontend/<label>) for accessibility purposes, as well as a **`name`**
attribute to represent the name of the associated data point submitted to the server. Each menu
option is defined by an **`<option>`** element nested inside the *`<select>`*.

Each *`<option>`* element should have a **`value`** attribute
containing the data value to submit to the
server when that option is selected; if no `value` attribute is included, the value defaults to
the text contained inside the element. You can include a **`selected`** attribute on an `<option>`
element to make it selected by default when the page first loads.

## Advanced `<select>` with Multiple Features

The `<select>` element has some unique attributes you can use to control it, such as **`multiple`** to
specify whether multiple options can be selected, and **`size`** to specify how many options should be
shown at once.
It also accepts most of the general form [`<input>`](/en/webfrontend/<input>) attributes
such as *`required`*, *`disabled`*, *`autofocus`*, etc.

You can further nest `<option>` elements inside **`<optgroup>`** elements to create
separate groups of options inside the dropdown.

!!! warn ""
    Note: `<optgroup>` elements may not be nested.

The follow example is more complex, showing off more features you can use
on a `<select>` element with **`multiple`** attribute:

```html
<label>Please choose one or more pets:
  <select name="pets" multiple size="4">
    <optgroup label="4-legged pets">
      <option value="dog">Dog</option>
      <option value="cat">Cat</option>
      <option value="hamster" disabled>Hamster</option>
    </optgroup>
    <optgroup label="Flying pets">
      <option value="parrot">Parrot</option>
      <option value="macaw">Macaw</option>
      <option value="albatross">Albatross</option>
    </optgroup>
  </select>
</label>
```

You'll see that:

- Multiple options are selectable because we've included the **`multiple`** attribute.
- The **`size`** attribute causes only 4 lines to display at a time; you can scroll to view all the options.
- We've included **`<optgroup`>** elements to divide the options up into different groups. This is a
purely visual grouping, its visualization generally consists of the group name being bolded,
and the options being indented.
- The "Hamster" option includes a **`disabled`** attribute and therefore can't be selected at all.

## Selecting Multiple Options

On a desktop computer, there are a number of ways to select multiple options in a `<select>`
element with a **`multiple`** attribute:

Mouse users can hold the !!!Ctrl!!!, !!!Command!!!, or !!!Shift!!! keys
(depending on what makes sense for your operating system) and then click
multiple options to select/deselect them.

!!! error ""
    Warning: The mechanism for selecting multiple non-contiguous items via the keyboard described below
    currently only seems to work in Firefox. Also note that on macOS, the !!!Ctrl!!! + !!!Up!!!
    and !!!Ctrl!!! + !!!Down!!! shortcuts conflict with the OS default shortcuts for Mission
    Control and Application windows, so you'll have to turn these off before it will work.

Keyboard users can select multiple contiguous items by:

- Focusing on the `<select>` element (e.g. using !!!Tab!!!).
- Selecting an item at the top or bottom of the range they want to select using
the !!!Up!!! and !!!Down!!! cursor keys to go up and down the options.
- Holding down the !!!Shift!!! key and then using the !!!Up!!!
and !!!Down!!! cursor keys to increase or decrease the range of items selected.

Keyboard users can select multiple non-contiguous items by:

- Focusing on the `<select>` element (e.g. using !!!Tab!!!).
- Holding down the !!!Ctrl!!! key then using the !!!Up!!! and !!!Down!!! cursor keys to
change the "focused" select option, i.e. the one that will be selected if you choose to do so. The
"focused" select option is highlighted with a dotted outline, in the same way as a keyboard-focused link.
- Pressing !!!Space!!! to select/deselect "focused" select options.

## `<datalist>` Usage

The `<datalist>` tag is used to provide "**autocomplete**" features
for *[`<input>`](/en/webfrontend/<input>)* elements.
The user can
see a *drop-down list*. The options in it are **predefined** and will be used as the user's input data.

Use the **`list`** attribute of the *[`<input>`](/en/webfrontend/<input>)* element
to bind the `<datalist>` element.

```html
<label for="myBrowser">Choose a browser from this list:</label>
<input list="browsers" id="myBrowser" name="myBrowser" />
<datalist id="browsers">
  <option value="Chrome">
  <option value="Firefox">
  <option value="Internet Explorer">
  <option value="Opera">
  <option value="Safari">
  <option value="Microsoft Edge">
</datalist>
```

## Styling With CSS

The `<select>` element is notoriously difficult to style productively with
CSS. You can affect
certain aspects like any element — for example, manipulating the box model,
the displayed font, etc., and you can use the
**`appearance`** property to remove the default system `appearance`.

However, these properties don't produce a consistent result across browsers, and it is hard to do
things like line different types of form element up with one another in a column. The `<select>`
element's internal structure is complex, and hard to control. If you want to get full control,
you should consider using a library with good facilities for styling form widgets (such as jQuery UI),
or try rolling your own dropdown menu using non-semantic elements, [[JavaScript]],
and WAI-ARIA to provide semantics.

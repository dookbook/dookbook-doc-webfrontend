TOPICS: <form>
        <input>
        <form> action attribute
        <form> method attribute
        <form> enctype attribute
        <form> novalidate attribute
        <form> target attribute
        <form> autocomplete attribute
        <form> accept-charset attribute
        <form> name attribute
        <input> type attribute
        <input> name attribute
        <input> value attribute
        <input> required attribute
        <input> maxlength attribute
        <input> minlength attribute
        <input> autofocus attribute
        <input> disabled attribute
        <input> readonly attribute
        <input> list attribute
        <input> form attribute
        <input> formaction attribute
        <input> formmethod attribute
        <input> formenctype attribute
        <input> formnovalidate attribute
        <input> formtarget attribute
        <input> checked attribute
        <input> autocomplete attribute
        <input> accept attribute
        <input> src attribute
        <input> alt attribute
        <input> width attribute
        <input> height attribute
        <input> placeholder attribute
        <input> size attribute
        <input> tabindex attribute

# HTML Form: `<form>` / `<input>`

The **HTML `<form>` element** represents a document section that contains **interactive controls** for
**submitting information** to a web server.

The **`<input>`** element is used to **create interactive controls for web-based forms** in order
to accept data from the user; a wide variety of types of input data and control widgets are available,
depending on the device and user agent.

## Technical Summary

| - | `<form>` | `<input>` |
| :-- | :-- | :-- |
| **Content categories** | *Flow content*, *palpable content*. | *Flow content*, *listed*, *submittable*, *resettable*, *form-associated element*, *phrasing content*. If the *`type`* is not *`hidden`*, then *labelable* element, *palpable content*. |
| **Permitted content** | *Flow content*, but not containing `<form>` elements. | None, it is an **[empty element](/en/webfrontend/Empty_Element)**. |
| **Tag omission** | None, both the starting and ending tag are mandatory. | Must have a start tag and must not have an end tag. |
| **Permitted parents** | Any element that accepts *flow content*. | Any element that accepts *phrasing content*. |
| **Permitted ARIA roles** | `group`, `presentation` | **`type=button`**: `link`,`menuitem`,`menuitemcheckbox`,`menuitemradio`,`radio`,`switch`,`tab`<br>**`checkbox`**: `button`,`menuitemcheckbox`,`option`,`switch`<br>**`image`**: `link`,`menuitem`,`menuitemcheckbox`,`menuitemradio`,`radio`,`switch`<br>**`radio`**: `menuitemradio`<br>**`color`**,**`file`**: None<br>**`text`**,**`password`**,**`hidden`**,**`submit`**,**`reset`**,**`email`**,**`url`**,**`tel`**,**`search`**: None<br>**`number`**,**`range`**: None<br>**`time`**,**`date`**,**`datetime`**,**`datetime-local`**,**`month`**,**`week`**: None |
| **DOM interface** | **`HTMLFormElement`** | **`HTMLInputElement`** |

## `<form>` Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| **`action`** | **The URI of a program that processes the form information**. This value can be overridden by a **`formaction`** attribute on a *[`<button>`](/en/webfrontend/<button>)* or *`<input>`* element. |
| **`method`** | The **[[HTTP]] method** that the browser uses to submit the form. Possible values are: **`post`** (*HTTP POST*), **`get`** (default. *HTTP GET*, not recommended), **`dialog`** (*[`<dialog>`](/en/webfrontend/<dialog>)*).<br><br>This value can be overridden by a **`formmethod`** attribute on a *[`<button>`](/en/webfrontend/<button>)* or *`<input>`* element. |
| `enctype` | When the value of the *`method`* attribute is *`post`*, it is the [MIME type](/en/glossary/MIME) of content that is used to submit the form to the server. Possible values are:<br><br>**`application/x-www-form-urlencoded`**: The *default* value if the attribute is not specified.<br>**`multipart/form-data`**: The value used for an `<input>` element with the *`type`* attribute set to *`file`*.<br>**`text/plain`**: (HTML5) Plain text.<br><br>This value can be overridden by a **`formenctype`** attribute on a *[`<button>`](/en/webfrontend/<button>)* or *`<input>`* element. |
| `novalidate` | This *Boolean* attribute indicates that the form is **not to be validated** when submitted. If this attribute is not specified (and therefore the form is validated), this default setting can be overridden by a **`formnovalidate`** attribute on a *[`<button>`](/en/webfrontend/<button>)* or *`<input>`* element belonging to the form. |
| `target` | A **name or keyword** indicating where to display the response that is received after submitting the form. See **[the attribute `target` of `<a>` element](/en/webfrontend/<a>)**.<br><br>HTML5: This value can be overridden by a formtarget attribute on a *[`<button>`](/en/webfrontend/<button>)* or *`<input>`* element. |
| `autocomplete` | Indicates whether input elements can by default have their values **automatically completed** by the browser. This setting can be overridden by an **`autocomplete`** attribute on an element belonging to the form. Possible values are:<br><br>**`off`**: The browser does not automatically complete entries.<br>**`on`**: The browser can automatically complete values based on values that the user has previously entered in the form. |
| `accept-charset` | A *space*- or *comma*-delimited list of character encodings that the server accepts. The browser uses them in the order in which they are listed. The default value, the reserved string **`"UNKNOWN"`**, indicates the same encoding as that of the document containing the form element. <br>In previous versions of HTML, the different character encodings could be delimited by spaces or commas. **In HTML5, only *spaces* are allowed as delimiters**. |
| `name` | The name of the form. In HTML 4, its use is deprecated (`id` should be used instead). It must be unique among the forms in a document and not just an empty string in HTML 5. |

## `<input>` Attributes

The `<input>` element is one of the most powerful and complex in all of HTML due to the sheer number
of combinations of input types and attributes. Since every `<input>` element, regardless of type,
is based on the *`HTMLInputElement`* interface, they technically all share the exact same set of
attributes. However, in reality, many attributes only function on specific input types, and some
input types support very few of these attributes. In addition,
some input types handle certain attributes in special ways.

### `<input>` Common Attributes

This includes the [global HTML attributes](/en/webfrontend/HTML_Global_Attributes),and as follows:

| Attribute | Description |
| :-- | :-- |
| **`type`** | A string indicating which **input type** the `<input>` element represents. |
| **`name`** | The **input's name**, to identify the input in the data submitted with the form's data. If not specified, or empty, the input's value is not submitted with the form. |
| **`value`** | The **input's current value**. |
| **`required`** | A *Boolean* which, if `true`, indicates that the input **must have a value** before the form can be submitted. If specified, **`:required`** pseudo-class applied, otherwise **`:optional`** pseudo-class. `<input>` of `type`: *`submit`*, *`hidden`*, *`button`*, *`reset`*, *`color`*, *`range`*, *`image`* NOT support it. |
| **`autofocus`** | A *Boolean* which, if present, makes the input **take focus** when the form is presented. An element with this attribute may gain focus before the *`DOMContentLoaded`* event is fired. `<input>` with `type="hidden"` NOT support it. |
| **`disabled`** | A *Boolean* attribute which is present if the `<input>` should be disabled. It does not receive the `click` event, and is not submitted with the form. |
| **`readonly`** | A *Boolean* attribute which, if `true`, indicates that the input **cannot be edited**. Only text controls can be made read-only, since for other controls (such as checkboxes and buttons) there is no useful distinction between being read-only (`readonly`) and being disabled (`disabled`), so the `readonly` attribute does not apply. |
| **`list`** | The **`id`** of a *[`<datalist>`](/en/webfrontend/<datalist>)* element that provides a list of suggested values for the input. |
| **`form`** | The **`id` of the `<form>`** of which the input is a member; if absent, the input is a member of the *nearest* containing form, or is not a member of a form at all. |
| `autocomplete` | A *string* indicating the type of **autocomplete functionality**, if any, to allow on the input. **`on`** for enabling autocomplete, **`off`** for disabling. Only support `<input>` elements with `type`: *`text`*, *`password`*, *`email`*, *`search`*, *`url`*, *`tel`*, *`date`*, *`datetime`*, *`datetime-local`*, *`range`*, and *`color`*. |
| `tabindex` | A numeric value providing guidance to the user agent as to the order in which controls receive focus when the user presses the !!!Tab!!! key. |

!!! warn "**`autofocus`** Usage Notes"
    **No more than one** element in the document may have the `autofocus` attribute.
    Warning: Automatically focusing a form control can confuse visually-impaired people using screen-reading
    technology. When `autofocus` is assigned, screen-readers "teleport" their user to the
    form control without warning them beforehand.

!!! warn "Attribute `required` and `readonly`"
    Note: The `required` attribute is not permitted on inputs with the `readonly` attribute specified.

!!! info "`disabled` vs `readonly`"
    The difference between `disabled` and `readonly` is that read-only controls can still function,
    whereas disabled controls generally do not function as controls until they are enabled.

### `tabindex` Attribute of `<input>`

An optional numeric value that defines both whether or not the `<input>` should be focusable
through use of the !!!Tab!!! key as well as whether or not the element participates in sequential focus
navigation. This value also establishes the order in which the element is
reached using the !!!Tab!!! key.

The values of **`tabindex`** have special meanings depending on sign:

- A **negative value** of `tabindex` indicates that the element should be focusable by the user,
but not using sequential keyboard navigation.
It's recommended to always use a value of *`-1`* as using other values can be complicated.
- A `tabindex` of **`0`** means that the element should be focusable and should be reachable by sequential
keyboard navigation, but that the tab order is left up to the user agent, which should apply the
user's platform conventions. This is usually the best value to use when you want an element to be
focusable and to participate in keyboard navigation rather than trying to manage the tab order yourself.
- A **positive value** of `tabindex` indicates the tabbing order of the element. Each time the user
presses the !!!Tab!!! key, the element with the next sequentially higher `tabindex` is focused.
Most platforms provide a reverse-tab feature, typically using the combination
of !!!Shift!!! + !!!Tab!!!, which reverses the tabbing order.
If `tabindex` is omitted or is not a valid integer, the user agent follows
platform conventions to determine what to do.

## Form `<input>` Types

How an `<input>` works varies considerably depending on the value of its **`type`** attribute.
If this attribute is not specified, the default type adopted is *`text`*.

The available types are as follows:

| `type` | Description |
| :-- | :-- |
| **`text`** | (*Default*) A **single-line text field**. Line-breaks are automatically *removed* from the input value. Use the **`placeholder`** attribute to specify the placeholder text within blank input content area and **`size`** attribute to specify the *maximum* length of the value that can be entered. |
| **`submit`** | **A button that submits the form**. |
| **`password`** | A *single-line* text field whose value is **obscured**. Use the **`maxlength`** and **`minlength`** attributes (optional) to specify the *maximum* / *minimum* length of the value that can be entered. |
| **`hidden`** | A control that is **not displayed** but whose value is submitted to the server. |
| **`checkbox`** | A **check box** allowing single values to be selected/deselected. Use the **`checked`** attribute (optional) to specify the *default selected* item.  |
| **`radio`** | A **radio button**, allowing a single value to be selected out of multiple choices. Use the **`checked`** attribute (optional) to specify the *default selected* item. |
| **`button`** | A push **button** with no default behavior. |
| **`reset`** | A *button* that **resets** the contents of the form to default values. |
| **`email`** | A field for editing an **e-mail address**. |
| **`url`** | A field for entering a **URL**. |
| **`tel`** | A control for entering a **telephone number**. |
| **`number`** | A control for entering a **number**. |
| **`range`** | A control for entering a number whose exact value is not important (in a range). |
| **`search`** | A *single-line text* field for entering **search** strings. Line-breaks are automatically removed from the input value. |
| **`color`** | A control for specifying a **color**. A color picker's UI has no required features other than accepting simple colors as text. |
| **`file`** | A control that lets the user **select a file**. Use the **`accept`** attribute to define the types of files that the control can select. |
| **`image`** | A **graphical submit button**. You must use the **`src`** attribute to define the source of the image and the **`alt`** attribute to define alternative text. You can use the **`height`** and **`width`** attributes to define the size of the image in *pixels*. |
| **`time`** | A control for entering a **time** value **with no time zone**. |
| **`date`** | A control for entering a **date** (year, month, and day, with no time). |
| **`datetime`** | A control for entering a **date and time**, **with time zone**. |
| **`datetime-local`** | A control for entering a **date and time**, **with no time zone**. |
| **`month`** | A control for entering a **month and year**, **with no time zone**. |
| **`week`** | A control for entering a **date consisting of a week-year number and a week number with no time zone**. |

```html
<!-- Example: Password -->
<input type="password">
<input type="password" maxlength="64" minlength="8">

<!-- Example: Hidden Input with value of 10 -->
<input type="hidden" value="10">

<!-- Example: Checkbox -->
<input type="checkbox" name="point" value="A1" checked>
<input type="checkbox" name="point" value="A2">

<!-- Example: Radio Button  -->
<input type="radio" name="sex" value="M" checked>
<input type="radio" name="sex" value="F">

<!-- Example: A button -->
<input type="button">

<!-- Example: A Reset button -->
<input type="reset">

<!-- Example: A email input -->
<input type="email">

<!-- Example: A URL input -->
<input type="url">

<!-- Example: A telephone number input -->
<input type="tel">

<!-- Example: A number input -->
<input type="number">

<!-- Example: A number within a range input -->
<input type="range">

<!-- Example: A search input -->
<input type="search">

<!-- Example: A color picker input -->
<input type="color">

<!-- Example: A file selector input -->
<input type="file">

<!-- Example: A image button -->
<input type="image" src="..." alt="alternative text">

<!-- Example: Time inputs -->
<input type="time">
<input type="date">
<input type="datetime">
<input type="datetime-local">
<input type="month">
<input type="week">
```

## Example: Simple Form

```html
<!-- Simple form which will send a POST request -->
<form action="" method="post">
  <input type="text" name="username">
  <input type="submit" value="Save">
</form>
```

This `name` is submitted along with the control's
value when the form data is submitted.
When an `<input>` element is given a `name`, that `name` becomes a property of the owning `<form>` element's
`HTMLFormElement.elements` property.

```javascript
let form = document.querySelector("form");
let userName1 = form.elements.username;
let userName2 = form.elements["username"];
```

## Styling Input Elements

It is possible to use the **`:valid`** and **`:invalid`** CSS pseudo-classes to style a form
element based on whether or not the individual elements within the form are valid.

You can style `<input>` elements using various color-related attributes in particular. One unusual
one that is specific to text entry-related elements is the CSS **`caret-color`** property,
which lets you set the color used to draw the text input caret:

```html
<input class="custom" size="32">
```

```css
input.custom {
  caret-color: red;
  font: 16px "Helvetica", "Arial", "sans-serif";
}
```

## `HTMLInputElement` Methods

The following methods are provided by the **`HTMLInputElement`** interface which represents
`<input>` elements in the DOM. Also available are those methods specified by the parent interfaces,
`HTMLElement`, `Element`, `Node`, and `EventTarget`.

| method | Description |
| :-- | :-- |
| `checkValidity()` | Immediately runs the validity check on the element, triggering the document to fire the `invalid` event at the element if the value isn't valid. |
| `reportValidity()` | Returns `true` if the element's value passes validity checks; otherwise, returns `false`.
| `select()` | Selects the entire content of the `<input>` element, if the element's content is selectable. For elements with no selectable text content (such as a visual color picker or calendar date input), this method does nothing. |
| `setCustomValidity()` | Sets a custom message to display if the input element's value isn't valid. |
| `setRangeText()` | Sets the contents of the specified range of characters in the input element to a given string. A `selectMode` parameter is available to allow controlling how the existing content is affected. |
| `setSelectionRange()` | Selects the specified range of characters within a textual input element. Does nothing for inputs which aren't presented as text input fields. |
| `stepDown()` | Decrements the value of a numeric input by one, by default, or by the specified number of units. |
| `stepUp()` | Increments the value of a numeric input by one or by the specified number of units. |

## Examples

```html
<!-- Form with fieldset, legend, and label -->
<form action="" method="post">
  <fieldset>
    <legend>Title</legend>
    <input type="radio" name="radio" id="radio">
    <label for="radio">Click me</label>
  </fieldset>
</form>
```

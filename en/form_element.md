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
        <label>
        <label> for attribute
        <label> form attribute

# HTML Form: `<form>`/`<input>`/`<label>`

The **HTML `<form>` element** represents a document section that contains **interactive controls** for
**submitting information** to a web server.

The **`<input>`** element is used to **create interactive controls for web-based forms** in order
to accept data from the user; a wide variety of types of input data and control widgets are available,
depending on the device and user agent.

The **`<label>`** element represents **a caption for an item** (*`<input>`* element) in a user interface.

It is possible to use the *`:valid`* and *`:invalid`* CSS pseudo-classes to style a `<form>`
element based on whether or not the individual elements within the form are valid.

## Technical Summary

| - | `<form>` | `<input>` | `<label>` |
| :-- | :-- | :-- | :-- |
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
| **`form`** | The **`id` of the `<form>`** of which the input is a member; if absent, the input is a member of the *nearest* containing form, or is not a member of a form at all. |
| `autocomplete` | A *string* indicating the type of **autocomplete functionality**, if any, to allow on the input. **`on`** for enabling autocomplete, **`off`** for disabling. Only support `<input>` elements with `type`: *`text`*, *`password`*, *`email`*, *`search`*, *`url`*, *`tel`*, *`date`*, *`datetime`*, *`datetime-local`*, *`range`*, and *`color`*. |
| `list` | The id of a [`<datalist>`](/en/webfrontend/<datalist>) element that provides a list of suggested values for the input
| `tabindex` | A numeric value providing guidance to the user agent as to the order in which controls receive focus when the user presses the Tab key. |

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

## Form `<input>` Types

How an `<input>` works varies considerably depending on the value of its **`type`** attribute.
If this attribute is not specified, the default type adopted is *`text`*.

The available types are as follows:

| `type` | Description |
| :-- | :-- |
| **`text`** | (*Default*) A **single-line text field**. Line-breaks are automatically *removed* from the input value. |
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

## `<label>` Usage Notes

Associating a `<label>` with an [`<input>`](/en/webfrontend/<input>) element offers some major advantages:

- The `<label>` text is not only visually associated with its corresponding text input;
it is programmatically associated with it too. This means that, for example, a screen reader will
read out the label when the user is focused on the form input, making it easier for an assistive
technology user to understand what data should be entered.
- You can click the associated label to focus/activate the input, as well as the input itself.
This increased hit area provides an advantage to anyone trying to activate the input, including
those using a touch-screen device.

Other Usage Notes:

- The form control that the `<label>` is labeling is called the labeled control of the `<label>` element.
One `<input>` can be associated with multiple labels.
- Labels are not themselves directly associated with forms. They are only indirectly associated
with forms through the controls with which they're associated.
- When a `<label>` is clicked or tapped and it is associated with a form control, the resulting
click event is also raised for the associated control.

### `<label>` Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*, *interactive content*, *form-associated element*, *palpable content*. |
| **Permitted content** | *Phrasing content*, but no descendant `<label>` elements. No labelable elements other than the labeled control are allowed. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *phrasing content*. |
| **Permitted ARIA roles** | None |
| **DOM interface** | **`HTMLLabelElement`** |

### `<label>` Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| **`for`** | The **`id`** of a labelable form-related element in the same document as the `<label>` element. If it is not labelable then the `for` attribute has no effect.<br>**Note:** A `<label>` element can have both a `for` attribute and a contained control element, as long as the `for` attribute points to the contained control element. |
| **`form`** | The [`<form>`](/en/webfrontend/<form>) element with which the label is associated (its form owner). If specified, the value of the attribute is the id of a [`<form>`](/en/webfrontend/<form>)  element in the same document. This lets you place label elements anywhere within a document, not just as descendants of their form elements. |

### Input with Associated Label

To associate the `<label>` with an [`<input>`](/en/webfrontend/<input>) element, you need to give the
[`<input>`](/en/webfrontend/<input>) an **`id`** attribute.
The `<label>` then needs a **`for`** attribute whose
value is the same as the `<input>`'s `id`.

The **first** element in the document with an `id` matching the value of the `for` attribute is the
labeled control for this `<label>` element, if it is a labelable element.
If there are other elements which also match the `id` value, later in the document, they are not considered.

```html
<!-- Example: Input with Associated Label -->
<form action="" method="post">
  <label for="username">Name:</label>
  <input id="username" type="text" name="username">
  <input type="submit" value="Save">
</form>
```

### Input Nested in Label

Alternatively, you can **nest** the [`<input>`](/en/webfrontend/<input>) directly inside the `<label>`,
in which case the `for` and `id` attributes are not needed because the association is implicit:

```html
<!-- Example: Input Nested in Label -->
<label>Name:
  <input type="text" name="username">
</label>
```

## `<label>` Accessibility Concerns

### Interactive Content in `<label>`

**Don't** place interactive elements such as *anchors* (*[`<a>`](/en/webfrontend/<a>)*)
or *buttons* (*[`<button`](/en/webfrontend/<button>)*) inside a `<label>`.
Doing so makes it difficult for people to activate the form `<input>` associated with the `<label>`.

Don't

```html
<label for="tac">
  <input id="tac" type="checkbox" name="terms-and-conditions">
  I agree to the <a href="terms-and-conditions.html">Terms and Conditions</a>
</label>
```

Do

```html
<label for="tac">
  <input id="tac" type="checkbox" name="terms-and-conditions">
  I agree to the Terms and Conditions
</label>
<p>
  <a href="terms-and-conditions.html">Read our Terms and Conditions</a>
</p>
```

### Headings in `<label>`

Placing heading elements within a `<label>` interferes with many kinds of assistive technology,
because headings are commonly used as a navigation aid. If the `<label>`'s text needs to be
adjusted visually, use CSS classes applied to the `<label>` element instead.

If a form, or a section of a form needs a title, use the *[`<legend>`](/en/webfrontend/<legend>)*
element placed within a *[`<fieldset>`](/en/webfrontend/<fieldset>)*.

Don't

```html
<label for="your-name">
  <h3>Your name</h3>
  <input id="your-name" name="your-name" type="text">
</label>
```

Do

```html
<label class="large-label" for="your-name">
  Your name
  <input id="your-name" name="your-name" type="text">
</label>
```

### Buttons Associated `<label>`

An *[`<input>`](/en/webfrontend/<input>)* element with a **`type="button"`** declaration
and a valid `value` attribute does not need a `<label>` associated with it.
Doing so may actually interfere with how assistive
technology parses the button input.
The same applies for the **[`<button>`](/en/webfrontend/<button>)** element.

***

### `<input>` Attributes2

**`list`**

The `id` of a [`<datalist>`](/en/webfrontend/<datalist>) element located in the same document which
provides a list of predefined values to suggest to the user for this input. Any values in the list
that are not compatible with the `type` are not included in the suggested options.

The `list` attribute is not supported by the `hidden`, `password`, `checkbox`, `radio`, `file`,
or any of the button types.

**`tabindex`**

An optional numeric value that defines both whether or not the input should be focusable through use
of the `<kbd>Tab</kbd>` key as well as whether or not the element participates in sequential focus
navigation. This value also establishes the order in which the element is
reached using the `<kbd>Tab</kbd>` key.

The values of `tabindex` have special meanings depending on sign:

- A negative value of `tabindex` indicates that the element should be focusable by the user, but not
using sequential keyboard navigation. It's recommended to always use a value
of -1 as using other values can be complicated.
- A `tabindex` of 0 means that the element should be focusable and should be reachable by sequential
keyboard navigation, but that the tab order is left up to the user agent, which should apply the
user's platform conventions. This is usually the best value to use when you want an element to be
focusable and to participate in keyboard navigation rather than trying to manage the tab order yourself.
- A positive value of `tabindex` indicates the tabbing order of the element. Each time the user
presses the `<kbd>Tab</kbd>` key, the element with the next sequentially higher `tabindex` is focused.
Most platforms provide a reverse-tab feature, typically using the combination
of `<kbd>Shift</kbd>` + `<kbd>Tab</kbd>`, which reverses the tabbing order.
If `tabindex` is omitted or is not a valid integer, the user agent follows
platform conventions to determine what to do.

### Methods

The following methods are provided by the `HTMLInputElement` interface which represents
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

### Styling Input Elements

You can style `<input>` elements using various color-related attributes in particular. One unusual
one that is specific to text entry-related elements is the CSS `caret-color` property,
which lets you set the color used to draw the text input caret:

```html
<label for="textInput">Note the red caret:</label>
<input id="textInput" class="custom" size="32">
```

```css
input.custom {
  caret-color: red;
  font: 16px "Helvetica", "Arial", "sans-serif";
}
```

For more information about adding color to elements in HTML,
see Applying color to HTML elements using CSS.

### Labels and Placeholders

TL;DR: To save you time, here's the key point: don't use the `placeholder` attribute if you can
avoid it. If you need to label an `<input>` element, use the [`<label>`](/en/webfrontend/<label>) element.

There are three seemingly similar ways to associate assistive text with an `<input>`. However,
they are actually quite different, and only one of them is always a good choice. Here we will look
at each of them and learn best practices for providing the user with guidance
when entering data into a form.

**The [`<label>`](/en/webfrontend/<label>) element**:

The [`<label>`](/en/webfrontend/<label>) element is the only way to provide explanatory information
about a form field that is always appropriate (aside from any layout concerns you have). It's never
a bad idea to use a [`<label>`](/en/webfrontend/<label>) to explain what should be entered into an
`<input>` or [`<textarea>`](/en/webfrontend/<textarea>).

**The placeholder attribute**:

The `placeholder` attribute lets you specify a text that appears within the `<input>`
element's content area itself when empty. It's intended to be used to show an example input,
rather than an explanation or prompt, but tends to be badly misused.

Here are two inputs that take a password, each with a placeholder:

Example of correct and incorrect placeholder usage

The first one uses a placeholder string `MyGr8P@sswrd`, demonstrating what a password might look like.
And no, that's not really a great password.

The second one uses a prompt string, `Enter your password` as a placeholder. The first, and most
obvious, problem with doing this is that as soon as the user types their first character, they no
longer have a prompt explaining what that field is for.

That's why, instead, you should use the [`<label>`](/en/webfrontend/<label>) element. The placeholder
should never be required in order to understand your forms. While some people are able to remember
what a given empty box is meant for after its only identifying text vanishes, others cannot.

If the user can't understand your form if the placeholders are missing (say, in a browser that
doesn't support placeholder, or in the case above where the user starts typing then gets confused),
you're not using placeholders properly.

In addition, browsers with automatic page translation features may skip over attributes when
translating. That means the `placeholder` may not get translated,
resulting in important information not being translated.

If you feel like you need to use a placeholder, it's possible to use both a placeholder and a label:

**Unadorned text adjacent to the `<input>` element**

You can also just have plain text adjacent to the `<input>` element, like this:

```html
<p>Enter your name: <input id="name" type="text" size="30"></p>
```

Please don't do this. This doesn't create a relationship between the prompt and the `<input>` element,
which is important for reasons we'll get into in the next section.

**Why you should use labels**:

In addition to the information provided above, there are a number of other reasons why
[`<label>`](/en/webfrontend/<label>) is the best way to explain `<input>`s:

The semantic pairing of `<input>` and [`<label>`](/en/webfrontend/<label>) elements is useful for
assistive technologies such as screen readers. By pairing them using the
[`<label>`](/en/webfrontend/<label>)'s for attribute, you bond the label to the input in a way that
lets screen readers describe inputs to users more precisely. By pairing a
[`<label>`](/en/webfrontend/<label>) with an `<input>`, clicking on either one will focus the `<input>`.
If you use plaintext to "label" your input, this won't happen. Having the prompt part of the
activation area for the input is helpful for people with motor control conditions.
As web developers, it's important that we never assume that people will know all the things that we
know. The diversity of people using the web—and by extension your web site—practically guarantees
that some of your site's visitors will have some variation in thought processes and/or circumstances
that leads them to interpret your forms very differently from you without
clear and properly-presented labels.

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

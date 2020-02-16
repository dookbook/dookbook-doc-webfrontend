TOPICS: <textarea>
        <textarea> rows attribute
        <textarea> cols attribute
        <textarea> name attribute
        <textarea> maxlength attribute
        <textarea> minlength attribute
        <textarea> required attribute
        <textarea> wrap attribute
        <textarea> autocomplete attribute
        <textarea> autofocus attribute
        <textarea> disabled attribute
        <textarea> readonly attribute
        <textarea> placeholder attribute
        <textarea> spellcheck attribute
        <textarea> form attribute

# HTML `<textarea>` Element

The **HTML `<textarea>` element** represents a **multi-line plain-text editing control**,
useful when you
want to allow users to enter a sizeable amount of free-form text, for example a comment on a
review or feedback form.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*, *Interactive content*, *listed, labelable, resettable, and submittable form-associated element*. |
| **Permitted content** | *Text* |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *phrasing content*. |
| **Permitted ARIA roles** | None |
| **DOM interface** | **`HTMLTextAreaElement`** |

## Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| **`rows`** | The number of **visible text lines** for the control. |
| **`cols`** | The **visible width** of the text control, in average character widths. If it is specified, it must be a *positive integer*. If it is not specified, the default value is *`20`*. |
| **`name`** | The **name** of the control. |
| **`maxlength`** | The **maximum number of characters** (*UTF-16* code units) that the user can enter. If this value isn't specified, the user can enter an *unlimited* number of characters. |
| **`minlength`** | The **minimum number of characters** (*UTF-16* code units) required that the user should enter. |
| **`wrap`** | Indicates how the control wraps text. Possible values are:<br><br>**`hard`:** The browser automatically inserts line breaks (CR+LF) so that each line has no more than the width of the control; the `cols` attribute must also be specified for this to take effect.<br>**`soft`:** The browser ensures that all line breaks in the value consist of a CR+LF pair, but does not insert any additional line breaks.<br>**`off`:** Like `soft` but changes appearance to white-space: pre so line segments exceeding `cols` are not wrapped and the `<textarea>` becomes horizontally scrollable.<br><br>If this attribute is not specified, *`soft`* is its default value. |
| **`placeholder`** | A **hint** to the user of what can be entered in the control. Carriage returns or line-feeds within the placeholder text must be treated as line breaks when rendering the hint. |
| `spellcheck` | Specifies whether the `<textarea>` is subject to spell checking by the underlying browser/OS. the value can be:<br>**`true`:** Indicates that the element needs to have its spelling and grammar checked.<br>**`default`:** Indicates that the element is to act according to a default behavior, possibly based on the parent element's own `spellcheck` value.<br>**`false`:** Indicates that the element should not be spell checked.

The `<textarea>` element also accepts several attributes common to form *[`<input>`](/en/webfrontend/<input>)*s,
such as **`form`**, **`autocomplete`**, **`autofocus`**, **`disabled`**, `placeholder`,
**`readonly`**, and **`required`**.

## Basic Usage

The following example show a very simple textarea, with a set numbers of rows and columns and
some default content.

```html
<label for="t">Label for textarea: </label>
<textarea id="t" name="textarea"
   rows="10" cols="50">Write something here</textarea>
```

The **`id`** attribute to allow the `<textarea>` to be associated with a *[`<label>`](/en/webfrontend/<label>)*
element for accessibility purposes, and a **`name`** attribute to set the name of the associated
data point submitted to the server when the form is submitted.

The **`rows`** and **`cols`** attributes allow you to specify an exact size for the `<textarea>` to take.
Setting these is a good idea for consistency, as browser defaults can differ.

If you want default content for your `<textarea>`, you enter it between the opening and closing
tags. `<textarea>` does not support the `value` attribute.

## Usage: Min and Max Length

**`maxlength`** specifies a maximum number of characters that the `<textarea>` is allowed to contain.
You can also set a minimum length that is considered valid using the **`minlength`** attribute,
and specify that the `<textarea>` will not submit (and is invalid) if it is empty, using the
**`required`** attribute.
This provides the `<textarea>` with simple validation, which is more basic than
the other form elements (for example, you can't provide specific regexs to validate the value against
using the *`pattern`* attribute, like you can with the [`<input>`](/en/webfrontend/<input>) element).

This example has a minimum and maximum number of characters — of `10` and `20` respectively.
Try it and see.

```html
<textarea name="textarea"
   rows="5" cols="30"
   minlength="10" maxlength="20">Write something here</textarea>
```

Note that *`minlength`* doesn't stop the user from removing characters so that the number entered goes
past the minimum, but it does make the value entered into the `<textarea>` invalid. Also note
that even if you have a `minlength` value set (3, for example), an empty `<textarea>` is still
considered valid unless you also have the *`required`* attribute set.

## Usage: Placeholder

This example has a **placeholder** set. Notice how it disappears when you start typing into the box.

```html
<textarea name="textarea"
   rows="5" cols="30"
   placeholder="Comment text."></textarea>
```

!!! warn ""
    Note: Placeholders should only be used to show an example of the type of data that should be
    entered into a form; they are not a substitute for a proper *[`<label>`](/en/webfrontend/<label>)*
    element tied to the input.

## Usage: Disabled and Readonly

This example shows two `<textarea>`s — one of which is **`disabled`**, and one of which is **`readonly`**.
Have a play with both and you'll see the difference in behavior — the `disabled` element is not
selectable in any way (and its value is not submitted), whereas the `readonly` element is selectable
and its contents copyable (and its value is submitted); you just can't edit the contents.

```html
<textarea name="textarea"
   rows="5" cols="30"
   disabled>I am a disabled textarea</textarea>

<textarea name="textarea"
   rows="5" cols="30"
   readonly>I am a readonly textarea</textarea>
```

## Styling With CSS

`<textarea>` is a replaced element — it has intrinsic dimensions, like a raster image.
By default, its **`display`** value is **`block`**. Compared to other form elements it is relatively
easy to style, with its box model, fonts, color scheme, etc. being easily manipulable using regular [[CSS]].

[Styling HTML forms](/en/webfrontend/<form>) provides some useful tips on styling `<textarea>`s.

### Baseline Inconsistency

The HTML specification doesn't define where the *baseline* of a `<textarea>` is, so different browsers
set it to different positions. Don't use *`vertical-align: baseline`* on it; the behavior is unpredictable.

### Resizable

In most browsers, `<textarea>`s are resizable — you'll notice the drag handle in the right hand
corner, which can be used to alter the size of the element on the page. This is controlled by the
**`resize`** CSS property — resizing is enabled by default, but you can explicitly disable it like:

```css
/* Example: disable <textarea> resizing */
textarea {
  resize: none;
}
```

### Styling Valid and Invalid Values

Valid and invalid values of a `<textarea>` element (e.g. those within, and outside the bounds
set by `minlength`, `maxlength`, or `required`) can be highlighted using the **`:valid`** and **`:invalid`**
pseudo-classes. For example, to give your textarea a different border depending on whether
it is valid or invalid:

```css
textarea:invalid {
  border: 2px dashed red;
}

textarea:valid {
   border: 2px solid lime;
}
```

## Other Form-Related Elements

- [`<form>`, `<input>`](/en/webfrontend/<form>)
- [`<label>`](/en/webfrontend/<label>)
- [`<fieldset>`, `<legend>`](/en/webfrontend/<fieldset>)
- [`<button>`](/en/webfrontend/<button>)
- [`<select>`, `<datalist>`, `<option>`, `<optgroup>`](/en/webfrontend/<select>)
- [`<output>`](/en/webfrontend/<output>)
- [`<progress>`](/en/webfrontend/<progress>)
- [`<meter>`](/en/webfrontend/<meter>)

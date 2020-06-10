TOPICS: <label>
        <label> for attribute
        <label> form attribute

# HTML `<label>` Element

The HTML **`<label>`** element represents **a caption for an item**
(*[`<input>`](/en/webfrontend/<input>)* element) in a user interface.

The `<label>` element does not present any special effects to the user. However, it improves
usability for mouse users. That is, when you use the label, just click the text area inside the
`<label>` element, this control will be triggered, and the browser will automatically focus on the
form control related to the label.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*, *interactive content*, *form-associated element*, *palpable content*. |
| **Permitted content** | *Phrasing content*, but no descendant `<label>` elements. No labelable elements other than the labeled control are allowed. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *phrasing content*. |
| **Permitted ARIA roles** | None |
| **DOM interface** | **`HTMLLabelElement`** |

## Attributes

The **`<label>`** element includes the [HTML global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| **`for`** | The **`id`** of a labelable form-related element in the same document as the `<label>` element. If it is not labelable then the `for` attribute has no effect.<br>**Note:** A `<label>` element can have both a `for` attribute and a contained control element, as long as the `for` attribute points to the contained control element. |
| **`form`** | The *[`<form>`](/en/webfrontend/<form>)* element with which the label is associated (its form owner). If specified, the value of the attribute is the **`id`** of a *[`<form>`](/en/webfrontend/<form>)* element in the same document. This lets you place `<label>` elements anywhere within a document, not just as descendants of their form elements. |

## `<label>` Usage Notes

Associating a *`<label>`* with an **[`<input>`](/en/webfrontend/<input>)** element
offers some major advantages:

- The `<label>` text is not only visually associated with its corresponding text input;
it is programmatically associated with it too. This means that, for example, a screen reader will
read out the label when the user is focused on the form input, making it easier for an assistive
technology user to understand what data should be entered.
- You can click the associated label to focus/activate the input, as well as the input itself.
This increased hit area provides an advantage to anyone trying to activate the input, including
those using a touch-screen device.

Other Usage Notes:

- The form control that the **`<label>`** is labeling is called the labeled control of
the `<label>` element. One *[`<input>`](/en/webfrontend/<input>)* can be associated with multiple labels.
- Labels are not themselves directly associated with forms. They are only indirectly associated
with forms through the controls with which they're associated.
- When a `<label>` is clicked or tapped and it is associated with a form control, the resulting
click event is also raised for the associated control.

### Input with Associated Label

To associate the *`<label>`* with an **[`<input>`](/en/webfrontend/<input>)** element,
you need to give the
*[`<input>`](/en/webfrontend/<input>)* an **`id`** attribute.
The `<label>` then needs a **`for`** attribute whose
value is the same as the [`<input>`](/en/webfrontend/<input>)'s `id`.

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

Alternatively, you can **nest** the *[`<input>`](/en/webfrontend/<input>)* directly inside the `<label>`,
in which case the *`for`* and *`id`* attributes are not needed because the association is implicit:

```html
<!-- Example: Input Nested in Label -->
<label>Name:
  <input type="text" name="username">
</label>
```

## Accessibility Concerns

### Interactive Content In `<label>`

**Don't** place interactive elements such as *anchors* (*[`<a>`](/en/webfrontend/<a>)*)
or *buttons* (*[`<button`](/en/webfrontend/<button>)*) inside a `<label>`.
Doing so makes it difficult for people
to activate the form [`<input>`](/en/webfrontend/<input>) associated with the `<label>`.

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

Placing **heading elements** within a *`<label>`* interferes with many kinds of assistive technology,
because headings are commonly used as a navigation aid. If the `<label>`'s text needs to be
adjusted visually, use [[CSS]] classes applied to the `<label>` element instead.

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
and a valid *`value`* attribute does not need a `<label>` associated with it.
Doing so may actually interfere with how assistive
technology parses the button input.
The same applies for the **[`<button>`](/en/webfrontend/<button>)** element.

## Labels and Placeholders

To save you time, here's the *key point*: don't use the **`placeholder`** attribute if you can
avoid it. If you need to label an *[`<input>`](/en/webfrontend/<input>)* element,
use the **`<label>`** element.

There are three seemingly similar ways to associate assistive text
with an *[`<input>`](/en/webfrontend/<input>)*.
However, they are actually quite different, and only one of them is always a good choice.
Here we will look at each of them and learn best practices for providing the user with guidance
when entering data into a form.

### The `<label>` Element

The **`<label>`** element is the only way to provide explanatory information
about a *`form`* field that is always appropriate (aside from any layout concerns you have). It's never
a bad idea to use a `<label>` to explain what should be entered into an
*[`<input>`](/en/webfrontend/<input>)* or *[`<textarea>`](/en/webfrontend/<textarea>)*.

### The `placeholder` Attribute

The **`placeholder`** attribute lets you specify a text that appears within the *[`<input>`](/en/webfrontend/<input>)*
element's content area itself when empty. It's intended to be used to show an example input,
rather than an explanation or prompt, but tends to be badly misused.

In addition, browsers with automatic page translation features may skip over attributes when
translating. That means the content of `placeholder` may not get translated,
resulting in important information not being translated.

If you feel like you need to use a `placeholder`, it's possible to use both a `placeholder` and a `<label>`:

### Unadorned Text Adjacent to The `<input>` Element

You can also just have plain text adjacent to the *[`<input>`](/en/webfrontend/<input>)* element,
like this:

```html
<p>Enter your name: <input id="name" type="text" size="30"></p>
```

Please don't do this. This doesn't create a relationship
between the prompt and the [`<input>`](/en/webfrontend/<input>) element.

### Why You Should Use Labels

In addition to the information provided above, there are a number of other reasons
why **`<label>`** is the best way to explain *[`<input>`](/en/webfrontend/<input>)*s:

The semantic pairing of [`<input>`](/en/webfrontend/<input>) and `<label>` elements is useful for
assistive technologies such as screen readers. By pairing them using the
`<label>`'s *`for`* attribute,
you bond the `<label>` to the [`<input>`](/en/webfrontend/<input>) in a way that
lets screen readers describe inputs to users more precisely.

By pairing a
`<label>` with an [`<input>`](/en/webfrontend/<input>), clicking on either one will focus the [`<input>`](/en/webfrontend/<input>).
If you use plaintext to "label" your input, this won't happen. Having the prompt part of the
activation area for the input is helpful for people with motor control conditions.

As Web developers, it's important that we never assume that people will know all the things that we
know. The diversity of people using the Web — and by extension your web site — practically guarantees
that some of your site's visitors will have some variation in thought processes and/or circumstances
that leads them to interpret your forms very differently from you without
clear and properly-presented labels.

## Browser compatibility

| - | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
| `<label>`| support | support | support |

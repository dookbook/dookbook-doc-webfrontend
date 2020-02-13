TOPICS: <fieldset>
        <legend>
        <fieldset> form attribute
        <fieldset> disabled attribute
        <fieldset> name attribute

# HTML `<fieldset>` / `<legend>` Element

The **HTML `<fieldset>` element** is used to **group several controls** as well as
labels (*[`<label>`](/en/webfrontend/<label>)*) within a web form.

The **HTML `<legend>` element** represents a **caption** for the content of its parent `<fieldset>`.

## Technical Summary

| - | `<fieldset>` | `<legend>` |
| :-- | :-- | :-- |
| **Content categories** | *Flow content*, *sectioning root*, *listed, form-associated element*, *palpable content*.| None. |
| **Permitted content** | An optional *`<legend>`* element, followed by *flow content*. | *Phrasing content*. |
| **Tag omission** | None, both the starting and ending tag are mandatory. | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *flow content*. | A *`<fieldset>`* whose **first child** is this element. |
| **Permitted ARIA roles** | `group`, `presentation` | None |
| **DOM interface** | **`HTMLFieldSetElement`** | **`HTMLLegendElement`** |

## `<fieldset>` Attributes

This element includes the [HTML global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| **`form`** | This attribute takes the value of the **`id`** attribute of a **[`<form>`](/en/webfrontend/<form>)** element you want the `<fieldset>` to be part of, even if it is not inside the form. |
| **`disabled`** | If this *Boolean* attribute is set, all form controls that are descendants of the `<fieldset>`, are disabled, meaning they are not editable but will be submitted along with [`<form>`](/en/webfrontend/<form>) in comparison with `disabled` attribute on form controls. They won't receive any browsing events, like mouse clicks or focus-related events. By default browsers display such controls grayed out. Note that form elements inside the `<legend>` element won't be disabled. |
| `name` | The name associated with the group. |

## Fieldset Usage

The **`<fieldset>`** element provides a grouping for a part of an HTML form,
with a nested **`<legend>`** element providing a *caption* for the *`<fieldset>`*. It takes few
attributes, the most notable of which are **`form`**, which can contain the *`id`* of a *[`<form>`](/en/webfrontend/<form>)*
on the same page, allowing you to make the `<fieldset>` part of that *[`<form>`](/en/webfrontend/<form>)*
even if it is not nested inside it, and **`disabled`**, which allows you to disable the
`<fieldset>` and all its contents in one go.

This example shows a really simple **`<fieldset>`** example, with a **`<legend>`**,
and two controls inside it.

```html
<form action="#" method="post">
  <fieldset>
    <!-- The caption for the `<fieldset>` is given
    by the first `<legend>` element nested inside it. -->
    <legend>Simple fieldset</legend>
    <label>Spirit of radio 1
      <input type="radio">
    </label>
    <label>Spirit of radio 2
      <input type="radio">
    </label>
  </fieldset>
</form>
```

### Disabled Fieldset

This example shows a **disabled** **`<fieldset>`** with two controls inside it. Note how both the controls
are disabled due to being inside a disabled `<fieldset>`.

```html
<form action="#" method="post">
  <fieldset disabled>  <!-- `disabled` attribute disable the fieldset -->
    <legend>Simple fieldset</legend>
    <label>Spirit of radio 1
      <input type="radio">
    </label>
    <label>Spirit of radio 2
      <input type="radio">
    </label>
  </fieldset>
</form>
```

## Styling with CSS

There are several special styling considerations for **`<fieldset>`**.

Its **`display`** value is **`block`** by default, and it establishes a block formatting context.
If the `<fieldset>` is styled with an inline-level `display` value, it will behave as **`inline-block`**,
otherwise it will behave as *`block`*. By default there is a *`2px`* groove border surrounding the contents,
and a small amount of default *`padding`*. The element has **`min-inline-size: min-content`** by default.

If a **`<legend>`** is present, it is placed over the block-start border. The `<legend>`
shrink-wraps, and also establishes a formatting context. The **`display`** value is **`blockified`**
(for example, `display: inline` behaves as `block`).

There will be an anonymous box holding the contents of the `<fieldset>`, which inherits certain
properties from the `<fieldset>`.
If the `<fieldset>` is styled with **`display: grid`** or **`display: inline-grid`**,
then the anonymous box will be a grid formatting context (*grid layouts*).
If the `<fieldset>` is styled with
**`display: flex`** or **`display: inline-flex`**,
then the anonymous box will be a flex formatting context (*flexbox layouts*).
Otherwise it establishes a block formatting context.

You can feel free to style the `<fieldset>` and `<legend>`
in any way you want to suit your page design.

TOPICS: <fieldset>
        <legend>

# `<fieldset>`

The **HTML `<fieldset>` element** is used to group several controls as well as
labels ([`<label>`](/en/webfrontend/<label>)) within a web form.

The `<fieldset>` element provides a grouping for a part of an HTML form,
with a nested `<legend>` element providing a caption for the `<fieldset>`. It takes few
attributes, the most notable of which are form, which can contain the id of a [`<form>`](/en/webfrontend/<form>)
on the same page, allowing you to make the `<fieldset>` part of that [`<form>`](/en/webfrontend/<form>)
even if it is not nested inside it, and disabled, which allows you to disable the
`<fieldset>` and all its contents in one go.

## Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| `disabled` | If this Boolean attribute is set, all form controls that are descendants of the `<fieldset>`, are disabled, meaning they are not editable but will be submitted along with [`<form>`](/en/webfrontend/<form>) in comparison with disabled attribute on form controls. They won't receive any browsing events, like mouse clicks or focus-related events. By default browsers display such controls grayed out. Note that form elements inside the `<legend>` element won't be disabled. |
| `form` | This attribute takes the value of the id attribute of a [`<form>`](/en/webfrontend/<form>) element you want the `<fieldset>` to be part of, even if it is not inside the form.
| `name` | The name associated with the group. |

!!! warn "Don't try this at home"
    Note: The caption for the fieldset is given by the first `<legend>` element nested inside it.

## Styling with CSS

There are several special styling considerations for `<fieldset>`.

Its `display` value is `block` by default, and it establishes a block formatting context.
If the `<fieldset>` is styled with an inline-level `display` value, it will behave as `inline-block`,
otherwise it will behave as block. By default there is a 2px groove border surrounding the contents,
and a small amount of default padding. The element has `min-inline-size: min-content` by default.

If a `<legend>` is present, it is placed over the block-start border. The `<legend>`
shrink-wraps, and also establishes a formatting context. The `display` value is blockified
(for example, `display: inline` behaves as `block`).

There will be an anonymous box holding the contents of the `<fieldset>`, which inherits certain
properties from the `<fieldset>`. If the `<fieldset>` is styled with `display: grid` or `display: inline-grid`,
then the anonymous box will be a grid formatting context. If the `<fieldset>` is styled with
`display: flex` or `display: inline-flex`, then the anonymous box will be a flex formatting context.
Otherwise it establishes a block formatting context.

You can feel free to style the `<fieldset>` and `<legend>`
in any way you want to suit your page design.

!!! warn "Don't try this at home"
    Note: as of this writing, there are bugs in Microsoft Edge and Google Chrome which prevent
    flexbox and grid layouts from being used inside a `<fieldset>`.
    [This GitHub issue](https://github.com/w3c/csswg-drafts/issues/321) provides bug tracking links.

## `<legend>`

The **HTML `<legend>` element** represents a caption for the content of its parent `<fieldset>`.

|  |  |
| :-- | :-- |
| **Content categories** | None. |
| **Permitted content** | *Phrasing content*. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | A `<fieldset>` whose first child is this `<legend>` element. |
| **Permitted ARIA roles** | None |
| **DOM interface** | **`HTMLLegendElement`** |

## Example

### Simple Fieldset

This example shows a really simple `<fieldset>` example, with a `<legend>`,
and a single control inside it.

```html
<form action="#">
  <fieldset>
    <legend>Simple fieldset</legend>
    <input type="radio" id="radio">
    <label for="radio">Spirit of radio</label>
  </fieldset>
</form>
```

### Disabled Fieldset

This example shows a disabled `<fieldset>` with two controls inside it. Note how both the controls
are disabled due to being inside a disabled `<fieldset>`.

```html
<form action="#">
  <fieldset disabled>
    <legend>Disabled fieldset</legend>
    <div>
      <label for="name">Name: </label>
      <input type="text" id="name" value="Chris">
    </div>
    <div>
      <label for="pwd">Archetype: </label>
      <input type="password" id="pwd" value="Wookie">
    </div>
  </fieldset>
</form>
```

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *sectioning root*, *listed, form-associated element*, *palpable content*.|
| **Permitted content** | An optional `<legend>` element, followed by *flow content*. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *flow content*. |
| **Permitted ARIA roles** | `group`, `presentation` |
| **DOM interface** | **`HTMLFieldSetElement`** |

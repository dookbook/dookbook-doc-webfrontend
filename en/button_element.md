TOPICS: <button>

# `<button>`

The **HTML `<button>` element** represents a clickable button, which can be used in forms or anywhere
in a document that needs simple, standard button functionality. By default, HTML buttons are
typically presented in a style similar to that of the host platform the user agent is running on,
but you can change the appearance of the button using CSS.

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*, *Interactive content*, listed, labelable, and submittable form-associated element, *palpable content*. |
| **Permitted content** | *Phrasing content* but there must be no Interactive content |
| **Tag omission** | None, both the starting and ending tag are mandatory.|
| **Permitted parents** | Any element that accepts *phrasing content*. |
| **Permitted ARIA roles** | `checkbox`, `link`, `menuitem`, `menuitemcheckbox`, `menuitemradio`, `radio`, `switch`, `tab` |
| **DOM interface** | **`HTMLButtonElement`** |

## Attributes

This element's attributes include the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| `autofocus` | This Boolean attribute lets you specify that the button should have input focus when the page loads, unless the user overrides it, for example by typing in a different control. Only one form-associated element in a document can have this attribute specified.
| `autocomplete` | The use of this attribute on a `<button>` is nonstandard and Firefox-specific. By default, unlike other browsers, [Firefox persists the dynamic disabled state](https://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing) of a `<button>` across page loads. Setting the value of this attribute to `off` (i.e. `autocomplete="off"`) disables this feature. See [bug 654072](https://bugzilla.mozilla.org/show_bug.cgi?id=654072).
| `disabled` |This Boolean attribute indicates that the user cannot interact with the button. If this attribute is not specified, the button inherits its setting from the containing element, for example [`<fieldset>`](/en/webfrontend/<fieldset>); if there is no containing element with the **disabled** attribute set, then the button is enabled.<br>Firefox will, unlike other browsers, by default, [persist the dynamic disabled state](https://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing) of a `<button>` across page loads. Use the `autocomplete` attribute to control this feature.
| `form` | The form element that the button is associated with (its form owner). The value of the attribute must be the id attribute of a [`<form>`](/en/webfrontend/<form>) element in the same document. If this attribute is not specified, the `<button>` element will be associated to an ancestor [`<form>`](/en/webfrontend/<form>) element, if one exists. This attribute enables you to associate `<button>` elements to [`<form>`](/en/webfrontend/<form>) elements anywhere within a document, not just as descendants of [`<form>`](/en/webfrontend/<form>) elements.
| `formaction` | The URI of a program that processes the information submitted by the button. If specified, it overrides the `action` attribute of the button's form owner.
| `formenctype` | If the button is a submit button, this attribute specifies the type of content that is used to submit the form to the server. Possible values are:<br>`application/x-www-form-urlencoded`: The default value if the attribute is not specified.<br>`multipart/form-data`: Use this value if you are using an [`<input>`](/en/webfrontend/<input>) element with the `type` attribute set to `file`.<br>`text/plain`<br>If this attribute is specified, it overrides the `enctype` attribute of the button's form owner.
| `formmethod` | If the button is a submit button, this attribute specifies the HTTP method that the browser uses to submit the form. Possible values are:<br>`post`: The data from the form are included in the body of the form and sent to the server.<br>`get`: The data from the form are appended to the form attribute URI, with a '?' as a separator, and the resulting URI is sent to the server. Use this method when the form has no side-effects and contains only ASCII characters.<br>If specified, this attribute overrides the `method` attribute of the button's form owner.
| `formnovalidate` | If the button is a submit button, this Boolean attribute specifies that the form is not to be validated when it is submitted. If this attribute is specified, it overrides the `novalidate` attribute of the button's form owner.
| `formtarget` |If the button is a submit button, this attribute is a name or keyword indicating where to display the response that is received after submitting the form. This is a name of, or keyword for, a browsing context (for example, tab, window, or inline frame). If this attribute is specified, it overrides the `target` attribute of the button's form owner. The following keywords have special meanings:<br>`_self`: Load the response into the same browsing context as the current one. This value is the default if the attribute is not specified.<br>`_blank`: Load the response into a new unnamed browsing context.<br>`_parent`: Load the response into the parent browsing context of the current one. If there is no parent, this option behaves the same way as `_self`.<br>`_top`: Load the response into the top-level browsing context (that is, the browsing context that is an ancestor of the current one, and has no parent). If there is no parent, this option behaves the same way as `_self`.
| `name` | The name of the button, which is submitted with the form data.
| `type` | The type of the button. Possible values are:<br>`submit`: The button submits the form data to the server. This is the default if the attribute is not specified, or if the attribute is dynamically changed to an empty or invalid value.<br>`reset`: The button resets all the controls to their initial values.<br>`button`: The button has no default behavior. It can have client-side scripts associated with the element's events, which are triggered when the events occur.
| `value` | The initial value of the button. It defines the value associated with the button which is submitted with the form data. This value is passed to the server in params when the form is submitted.

## Notes

`<button>` elements are much easier to style than [`<input>`](/en/webfrontend/<input>) elements.
You can add inner HTML content (think [`<em>`](/en/webfrontend/<em>), [`<strong>`](/en/webfrontend/<strong>)
or even [`<img>`](/en/webfrontend/<img>)), and make use of `::after` and `::before` pseudo-element
to achieve complex rendering while [`<input>`](/en/webfrontend/<input>) only accepts a text value attribute.

If your buttons are not to submit form data to a server, be sure to set their type attribute to button.
Otherwise they will try to submit form data and to load the (nonexistent) response, possibly
destroying the current state of the document.

!!! error "Don't try this at home"
    Internet Explorer 7 has a bug where when submitting a form with
    `<button type="submit" name="myButton" value="foo">Click me</button>`, the POST data sent will result
    in `myButton=Click me` instead of `myButton=foo`. The problem is even worse in Internet Explorer
    6, in which submitting a form through a button submits all of the form's buttons with the same problem
    as in Internet Explorer 7. These issues have been fixed in Internet Explorer 8.

!!! warn "Don't try this at home"
    Firefox will, unlike other browsers, by default, [persist the dynamic disabled state](https://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing)
    of a `<button>` across page loads. Setting the value of the `autocomplete` attribute to
    off disables this feature. See [bug 654072](https://bugzilla.mozilla.org/show_bug.cgi?id=654072).

Versions of Firefox for Android prior to version 35 have a default `background-image`
gradient set on all buttons (see [bug 763671](https://bugzilla.mozilla.org/show_bug.cgi?id=763671)).
This can be disabled using `background-image: none`.

## Example

```html
<button name="button">Click me</button>
```

## Accessibility Concerns

### Icon buttons

Buttons that only use an icon to represent functionality do not have an accessible name. Accessible
names provide a programmatic hook for assistive technology such as screen readers to access when
they parse the document and generate an accessibility tree. Assistive technology then uses the
accessibility tree to navigate and manipulate page content.

To give an icon button an accessible name, supply a string of text for the `<button>` element that
concisely describes the button's functionality.

`Example`

```html
<button name="favorite" type="button">
  <svg aria-hidden="true" viewBox="0 0 10 10"><path d="M7 9L5 8 3 9V6L1 4h3l1-3 1 3h3L7 6z"/></svg>
  Add to favorites
</button>
```

If you want to visually hide the button's text, an accessible way to do so is to use
[a combination of properties](https://gomakethings.com/hidden-content-for-better-a11y/#hiding-the-link)
to remove it visually from the screen but keep it parseable by assistive technology.

However, it is worth noting that leaving the button text visually apparent can aid people who may not
be familiar with the icon's meaning or understand the button's purpose. This is especially relevant
for people who are not as technologically sophisticated, or who may have different cultural
interpretations for the imagery the icon button uses.

- [What is an accessible name? | The Paciello Group](https://developer.paciellogroup.com/blog/2017/04/what-is-an-accessible-name/)
- [MDN Understanding WCAG, Guideline 4.1 explanations](https://wiki.developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Robust#Guideline_4.1_%E2%80%94_Compatible_Maximize_compatibility_with_current_and_future_user_agents_including_assistive_technologies)
- [Understanding Success Criterion 4.1.2 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/ensure-compat-rsv.html)

### Size and Proximity

Size

Interactive elements such as buttons should provide an area large enough that it is easy to activate
them. This helps a variety of people, including people with motor control issues and people using
non-precise forms of input such as a stylus or fingers. A minimum interactive size of 44 by 44
[CSS pixels](https://www.w3.org/TR/WCAG21/#dfn-css-pixels) is recommended.

- [Understanding Success Criterion 2.5.5: Target Size | W3C Understanding WCAG 2.1](https://www.w3.org/WAI/WCAG21/Understanding/target-size.html)
- [Target Size and 2.5.5 | Adrian Roselli](http://adrianroselli.com/2019/06/target-size-and-2-5-5.html)
- [Quick test: Large touch targets - The A11Y Project](https://a11yproject.com/posts/large-touch-targets/)

Proximity

Large amounts of interactive content—including buttons—placed in close visual proximity to each other
should have space inserted to separate them. This spacing is beneficial for people who are
experiencing motor control issues, who may accidentally activate the wrong interactive content.

Spacing may be created using CSS properties such as `margin`.

- [Hand tremors and the giant-button-problem - Axess Lab](https://axesslab.com/hand-tremors/)

### Firefox

Firefox will add a small dotted border on a focused button. This border is declared through CSS,
in the browser stylesheet, but you can override it if necessary to add your own focused style using
`button::``-moz-focus-inner` `{ }`.

If overridden, it is important to ensure that the state change when focus is moved to the button is
high enough that people experiencing low vision conditions will be able to perceive it.

Color contrast ratio is determined by comparing the luminosity of the button text and background
color values compared to the background the button is placed on. In order to meet current
[Web Content Accessibility Guidelines (WCAG)](https://www.w3.org/WAI/intro/wcag), a ratio of 4.5:1
is required for text content and 3:1 for larger text such as headings. Large text is defined as
18.66px and `bold` or larger, or 24px or larger.

- [WebAIM: Color Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [MDN Understanding WCAG, Guideline 1.4 explanations](https://wiki.developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#Guideline_1.4_Make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.3 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html)

### Clicking and focus

Whether clicking on a `<button>` causes it to (by default) become focused varies by browser and OS.
The results for [`<input>`](/en/webfrontend/<input>) of `type="button"` and `type="submit"` were
the same.

**Does clicking on a `<button>` give it the focus?**

| Desktop Browsers | Windows 8.1 | OS X 10.X |
| :-- | :-- | :-- |
| Firefox | Yes - Firefox 30.0 | No (even with a tabindex) Firefox 63 |
| Chrome | Yes - Chrome 35 | Yes - Chrome 65 |
| Safari | N/A | No (even with a tabindex) Safari 12 |
| Internet Explorer | Yes - Internet Explorer 11 N/A |
| Presto | Yes - Opera 12 | Yes - Opera 12 |

**Does tapping on a `<button>` give it the focus?**

| Mobile Browsers | iOS 7.1.2 | Android 4.4.4 |
| :-- | :-- | :-- |
| Safari Mobile | No (even with a tabindex) | N/A |
| Chrome 35 | No (even with a tabindex) | Yes |

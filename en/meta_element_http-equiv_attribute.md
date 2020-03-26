TOPICS: <meta> http-equiv attribute  <!-- markdownlint-disable proper-names -->
<!-- markdownlint-enable proper-names -->

# `http-equiv` Attribute of `<meta>` Element

Define a **pragma directive**. The attribute is named *"`http-equiv`(alent)"* because all the allowed
values are names of particular **HTTP headers**.

## `content-language`

!!! error "It is obsolete"
    Prefer the `lang` attribute on the [`<html>`](/en/webfrontend/<html>) element.

## `content-security-policy`

Define a **content policy** for the current page. Content policies mostly
specify allowed server origins and script endpoints which help guard against
*cross-site scripting attacks*.

## `content-type`

!!! error "It is obsolete"
    Use the `charset` attribute on the [`<meta>`](/en/webfrontend/<meta>) element instead.

## `refresh`

This instruction specifies:

1. The **number of seconds until the page should be reloaded** - only if the `content` attribute
   contains a *positive integer*.
2. The **number of seconds until the page should redirect to another** - only if the `content`
   attribute contains a *positive integer* followed by the string '`;url=`', and a valid URL.

"`refresh`" should be used sparingly because it leaves the page out of user control. Using "`refresh`"
in the [W3C's Web Content Accessibility Guide](http://www.w3.org/WAI/intro/wcag.php) will fail.

### Refreshing Content Examples

```html
<!-- Redirect page after 3 seconds -->
<meta http-equiv="refresh" content="3">
<meta http-equiv="refresh" content="3;url=https://dookbook.info">
```

### Accessibility Concerns for Refreshing Content

Pages set with a refresh value run the risk of having the time interval being too short. People
navigating with the aid of assistive technology such as a screen reader may be unable to read through
and understand the page's content before being automatically redirected. The abrupt, unannounced
updating of the page content may also be disorienting for people experiencing low vision conditions.

- [MDN Understanding WCAG, Guideline 2.1 explanations](https://wiki.developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Operable#Guideline_2.2_%E2%80%94_Enough_Time_Provide_users_enough_time_to_read_and_use_content)
- [MDN Understanding WCAG, Guideline 3.1 explanations](https://wiki.developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Understandable#Guideline_3.2_%E2%80%94_Predictable_Make_Web_pages_appear_and_operate_in_predictable_ways)
- [Understanding Success Criterion 2.2.1 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/time-limits-required-behaviors.html)
- [Understanding Success Criterion 2.2.4 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/time-limits-postponed.html)
- [Understanding Success Criterion 3.2.5 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/consistent-behavior-no-extreme-changes-context.html)

## `default-style`

Specifies a predefined style sheet to be used.

```html
<meta http-equiv="default-style" content="the document's preferred stylesheet">
```

**Note**: The value of the `content` attribute in the example must match the value of the `title`
attribute on a [`link`](/en/webfrontend/<link>) element in the same document, or the value of the
 `title` attribute on a [`style`](/en/webfrontend/<style>) element in the same document.

## `set-cookie`

!!! error "It is obsolete"
    Use the HTTP header `Set-Cookie` instead.

## `X-UA-Compatible`

Determine which version of the browser to use to render the current page.

```html
<!-- latest version of IE and Chrome -->
<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
```

TOPICS: title attribute

# HTML Global Attribute: `title`

The **`title`** [global attribute](/en/webfrontend/HTML_Global_Attributes) contains text representing
advisory information related to the element it belongs to.

Some typical uses:

- **Link**: the title or description of the linked document
- **Media element**: eg image: description or related information
- **Paragraphs**: footnotes or related comments
- **Citations**: author information, and others

Additional semantics are attached to the title attributes of the [`<link>`](/en/webfrontend/<link>),
[`<abbr>`](/en/webfrontend/<abbr>), [`<input>`](/en/webfrontend/<input>), and
[`<menuitem>`](/en/webfrontend/<menuitem>) elements.

## Multiline titles

The `title` attribute may contain several lines. Each `U+000A LINE FEED` (`LF`) character represents
a line break. Some caution must be taken, as this means the following renders across two lines:

```html
<p>Newlines in <code>title</code> should be taken into account,
like <abbr title="This is a
multiline title">example</abbr>.</p>
```

## Title attribute inheritance

If an element has no `title` attribute, then it inherits it from its parent node, which in turn may
inherit it from its parent, and so on.

If this attribute is set to the empty string, it means its ancestors' `title`s are irrelevant and
shouldn't be used in the tooltip for this element.

```html
<div title="CoolTip">
  <p>Hovering here will show “CoolTip”.</p>
  <p title="">Hovering here will show nothing.</p>
</div>
```

## See also

- All HTML [global attributes](/en/webfrontend/HTML_Global_Attributes).
- `HTMLElement.title` that reflects this attribute.

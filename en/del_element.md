TOPICS: <del>
        <del> cite attribute
        <del> datetime attribute

# HTML Deleted Element: `<del>`

The **HTML `<del>` element** represents a range of text that has been **deleted** from a document.
This can be used when rendering "*track changes*" or source code diff information, for example.
The *[`<ins>`](/en/webfrontend/<ins>)* element can be used for the opposite purpose:
to indicate text that has been added to the document.

This element is often (but need not be) rendered by applying a
*strike-through* style (*`text-decoration: line-through`* in CSS) to the text.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Phrasing content* or *flow content*. |
| **Permitted content**| *Transparent*. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *phrasing content*. |
| **Permitted ARIA roles**| Any |
| **DOM interface** | **`HTMLModElement`** |

## Attributes

This element's attributes include the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| **`cite`** | A URI for a resource that **explains the change** (for example, meeting minutes). |
| **`datetime`** | This attribute indicates **the time and date of the change** and must be a valid date string with an optional time. If the value cannot be parsed as a date with an optional time string, the element does not have an associated time stamp. |

## Examples

```html
<p><del>This text has been deleted</del>,
here is the rest of the paragraph.</p>
<del><p>This paragraph has been deleted.</p></del>
```

## Accessibility Concerns

The presence of the del element is not announced by most screen reading technology in its default
configuration. It can be made to be announced by using the CSS **`content`** property, along
with the **`::before`** and **`::after`** pseudo-elements.

```css
del::before,
del::after {
  clip-path: inset(100%);
  clip: rect(1px, 1px, 1px, 1px);
  height: 1px;
  overflow: hidden;
  position: absolute;
  white-space: nowrap;
  width: 1px;
}

del::before {
  content: " deletion start] ";
}

del::after {
  content: " deletion end] ";
}
```

Some people who use screen readers deliberately disable announcing content that creates extra
verbosity. Because of this, it is important to not abuse this technique and only apply it in
situations where not knowing content has been deleted would adversely affect understanding.

- [Short note on making your mark (more accessible) | The Paciello Group](https://developer.paciellogroup.com/blog/2017/12/short-note-on-making-your-mark-more-accessible/)
- [Tweaking Text Level Styles | Adrian Roselli](http://adrianroselli.com/2017/12/tweaking-text-level-styles.html)

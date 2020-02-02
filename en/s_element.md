TOPICS: <s>

# HTML Strikethrough Element: `<s>`

The **HTML `<s>` element** renders **text with a strikethrough**, or a line through it. Use the `<s>`
element to represent things that are **no longer relevant or no longer accurate**.
However, `<s>` is not appropriate when indicating document edits; for that, use the
*[`<del>`](/en/webfrontend/<del>)* and *[`<ins>`](/en/webfrontend/<ins>)* elements, as appropriate.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Phrasing content* or *flow content*. |
| **Permitted content** | *Phrasing content*. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *phrasing content*. |
| **Permitted ARIA roles** | Any |
| **DOM interface** | **`HTMLElement`** |

## Attributes

This element only includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

## Example

```html
<s>Today's Special: Salmon</s> SOLD OUT<br>
<span style="text-decoration:line-through;">Today's Special:
  Salmon</span> SOLD OUT
```

## Accessibility Concerns

The presence of the `<s>` element is not announced by most screen reading technology in its default
configuration. It can be made to be announced by using the CSS **`content`** property, along with
the **`::before`** and **`::after`** pseudo-elements.

```css
s::before,
s::after {
  clip-path: inset(100%);
  clip: rect(1px, 1px, 1px, 1px);
  height: 1px;
  overflow: hidden;
  position: absolute;
  white-space: nowrap;
  width: 1px;
}

s::before {
  content: " start of stricken text] ";
}

s::after {
  content: " end of stricken text] ";
}
```

Some people who use screen readers deliberately disable announcing content that creates extra
verbosity. Because of this, it is important to not abuse this technique and only apply it in
situations where not knowing content has been struck out would adversely affect understanding.

- [Short note on making your mark (more accessible) | The Paciello Group](https://developer.paciellogroup.com/blog/2017/12/short-note-on-making-your-mark-more-accessible/)
- [Tweaking Text Level Styles | Adrian Roselli](http://adrianroselli.com/2017/12/tweaking-text-level-styles.html)

TOPICS: :link
        :visited
        :hover
        :active

# CSS Pseudo-Class: `:link`、`:visited`、`:hover`、`:active`

The **`:link`** CSS pseudo-class represents an element that has **not yet been visited**. It matches
every unvisited [*`<a>`*](/en/webfrontend/<a>), [*`<area>`*](/en/webfrontend/<area>), or
[*`<link>`*](/en/webfrontend/<link>) element that has an **`href`** attribute.

The **`:visited`** CSS pseudo-class represents links that the user has **already visited**. For privacy
reasons, the styles that can be modified using this selector are very limited.

The **`:hover`** CSS pseudo-class matches when the user interacts with an element with a pointing
device, but does not necessarily activate it. It is generally triggered when the user **hovers over**
an element with the *cursor* (mouse pointer).

The **`:active`** CSS pseudo-class represents an element (such as a *button*) that is **being activated**
by the user. When using a mouse, "activation" typically starts when the user *presses down* the
primary mouse *button*.

!!! warn "Note"
    Please define in the order defined by *LVHA*-order: `:link` — `:visited` — `:hover` — `:active`.

## Example

```html
<a href="#">dookbook</a>
```

```css
a:link { color: #FF0000; } /* Unvisited links */
a:visited { color: #00FF00; } /* Visited link */
a:hover { color: #FF00FF; } /* Mouse over link */
a:active { color: #0000FF; } /* Selected link */
```

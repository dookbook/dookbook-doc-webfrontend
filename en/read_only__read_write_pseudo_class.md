TOPICS: :read-only
        :read-write
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Pseudo-Class: `:read-only`、`:read-write`

The **`:read-only`** CSS pseudo-class represents an element (such as input or textarea) that is not
editable by the user.

!!! warn "Note"
    This selector doesn't just select [`<input>`](/en/webfrontend/<input>)/[`<textarea>`](/en/webfrontend/<textarea>)
    with `readonly` set on them; it will select any element that cannot be edited by the user.

The **`:read-write`** CSS pseudo-class represents an element (such as `input` or `textarea`) that
is editable by the user.

!!! warn "Note"
     This selector doesn't just select [`<input>`](/en/webfrontend/<input>)/[`<textarea>`](/en/webfrontend/<textarea>)
     it will select any element that can be edited by the user, such as a [`<p>`](/en/webfrontend/<p>)
     element with `contenteditable` set on it.

## 示例: `:read-only`

```html
<input type="text" value="Type whatever you want here.">
<input type="text" value="This is a read-only field." readonly>
<p>This is a normal paragraph.</p>
<p contenteditable="true">You can edit this paragraph!</p>
```

```css
input { min-width: 25em; }
input:-moz-read-only { background: cyan; }
input:read-only { background: cyan; }

p:-moz-read-only { background: lightgray; }
p:read-only { background: lightgray; }
p[contenteditable="true"] { color: blue; }
```

## 示例: `:read-write`

```html
<input type="text" value="Type whatever you want here.">
<input type="text" value="This is a read-only field." readonly>
<p>This is a normal paragraph.</p>
<p contenteditable="true">You can edit this paragraph!</p>
```

```css
input { min-width: 25em; }
input:-moz-read-write { background: cyan; }
input:read-write { background: cyan; }

p:-moz-read-write { background: lightgray; }
p:read-write { background: lightgray; }
p[contenteditable="true"] { color: blue; }
```

TOPICS: :active
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Pseudo-Class: `:active`

The **`:active`** CSS pseudo-class represents an element (such as a button) that is being activated
by the user. When using a mouse, "activation" typically starts when the user presses down the
primary mouse button.

```css
/* Selects any <a> that is being activated */
a:active {
  color: red;
}
```

The `:active` pseudo-class is commonly used on [`<a>`](/en/webfrontend/<a>) and [`<button>`](/en/webfrontend/<button>)
elements. Other common targets of this pseudo-class include elements that contain an activated element,
and form elements that are being activated through their associated [<label>](/en/webfrontend/<label>).

Styles defined by the `:active` pseudo-class will be overridden by any subsequent link-related
pseudo-class (`:link`, `:hover`, or `:visited`) that has at least equal specificity. To style links
appropriately, put the `:active` rule after all other link-related rules, as defined by the LVHA-order:
`:link` — `:visited` — `:hover` — `:active`.

!!! warn "Note"
    On systems with multi-button mice, CSS3 specifies that the `:active` pseudo-class must only
    apply to the primary button; on right-handed mice, this is typically the leftmost button.

## Active links

```html
<p>This paragraph contains a link:
  <a href="#">This link will turn red while you click on it.</a>
  The paragraph will get a gray background while you click on it or the link.
</p>
```

```css
a:link { color: blue; }          /* Unvisited links */
a:visited { color: purple; }     /* Visited links */
a:hover { background: yellow; }  /* Hovered links */
a:active { color: red; }         /* Active links */

p:active { background: #eee; }   /* Active paragraphs */
```

## Active form elements

```html
<form>
  <label for="my-button">My button: </label>
  <button id="my-button" type="button">Try Clicking Me or My Label!</button>
</form>
```

```css
form :active {
  color: red;
}

form button {
  background: white;
}
```

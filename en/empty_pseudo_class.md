TOPICS: :empty
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Pseudo-Class: `:empty`

The **`:empty`** CSS pseudo-class represents any element that has no children. Children can be
either element nodes or text (including whitespace). Comments, processing instructions, and CSS
`content` do not affect whether an element is considered empty.

!!! warn "Note"
    In Selectors Level 4 the `:empty` pseudo-class was changed to act like `:-moz-only-whitespace`,
    but no browser currently supports this yet.

## Examples

```html
<div class="box"><!-- I will be lime. --></div>
<div class="box">I will be pink.</div>
<div class="box">
  <!-- I will be pink in older browsers because of the whitespace around this comment. -->
</div>
<div class="box">
  <p><!-- I will be pink in all browsers because of the non-collapsible whitespace and elements around this comment. --></p>
</div>
```

```css
.box {
  background: pink;
  height: 80px;
  width: 80px;
}

.box:empty {
  background: lime;
}
```

TOPICS: order property

# CSS Property: `order`

The CSS **`order`** property specifies the order in which flexible items in a flexible container are
laid out. Elements are laid out in increasing order of the value of the **`order`** property. Elements
with the same **`order`** property value are laid out in the order they appear in the source code.

!!! warn "Note"
    **`order`** only affects the visual order of the elements (**visual order**) and does not affect
    the logic or tab order of the elements. **`order`** cannot be used for non-visual media,
    such as speech.

## Property value

| Property value | Description |
| :--- | :--- |
| **integer** | Indicates the order group in which this scalable item is located.|

## Examples

```html
<div id='main'>
   <article>1…</article>
   <nav>2…</nav>
   <aside>3…</aside>
</div>
<footer>4…</footer>
```

The CSS code below will create a classic double sidebar layout around a central content block. The
Flexible Box layout module automatically creates three content blocks with the same height, and also
uses all available horizontal space.

```css
#main { display: flex; }
#main > article { flex:1;         order: 2; }
#main > nav     { width: 200px;   order: 1; }
#main > aside   { width: 200px;   order: 3; }
```

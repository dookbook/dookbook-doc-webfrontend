TOPICS: overflow property
        overflow-x property
        overflow-y property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Controlling Content Overflow Property: `overflow`

The **`overflow`** shorthand CSS property sets what to do when an element's content is too big to
fit in its block formatting context. It is a shorthand for **`overflow-x`** and **`overflow-y`**.

The options include clipping, showing scrollbars, or displaying the content flowing out of its
container into the surrounding area.

Specifying a value other than `visible` (the default) creates a new block formatting context. This
is necessary for technical reasons — if a float intersected with the scrolling element it would
forcibly rewrap the content after each scroll step, leading to a slow scrolling experience.

In order for `overflow` to have an effect, the block-level container must have either a set height
(`height` or `max-height`) or `white-space` set to `nowrap`.

!!! warn "Note"
    Setting one axis to `visible` (the default) while setting the other to a different value results
    in `visible` behaving as `auto`.

!!! warn "Note"
    The JavaScript `Element.scrollTop` property may be used to scroll an HTML element even when
    `overflow` is set to `hidden`.

The `overflow` property is specified as one or two keywords chosen from the list of values below.
If two keywords are specified, the first applies to `overflow-x` and the second to `overflow-y`.
Otherwise, both `overflow-x` and `overflow-y` are set to the same value.

!!! warn "Note"
    Prior to Firefox 63, these values were reversed, with the first value applied to `overflow-x`
    and the second value applied to `overflow-y`. Firefox 63 updated this order to match changes to
    the specification. This change is to match the order when using the new logical properties
    `overflow-block` and `overflow-inline`.

## CSS Property `overflow-x`

The **`overflow-x`** CSS property sets what shows when content overflows a block-level element's
left and right edges. This may be nothing, a scroll bar, or the overflow content.

## CSS Property `overflow-y`

The **`overflow-y`** CSS property sets what shows when content overflows a block-level element's
top and bottom edges. This may be nothing, a scroll bar, or the overflow content.

## Common Property Value

| Property Value | Description |
| :--- | :--- |
| **`visible`** | **Content is not clipped** and may be rendered outside the padding box. |
| **`hidden`** | If necessary, the content will be trimmed to fit the filled box. **No scroll bar is provided**. |
| **`scroll`** | Content is clipped if necessary to fit the padding box. **Browsers always display scrollbars** whether or not any content is actually clipped, preventing scrollbars from appearing or disappearing as content changes. Printers may still print overflowing content |
| **`auto`** | Depends on the user agent. If content fits inside the padding box, it looks the same as visible, but still establishes a new block formatting context. Desktop browsers provide scrollbars if content overflows. |

### Shorthand Example

```css
p {  
  width: 12em;
  height: 6em;
  border: dotted;
  overflow: visible; /* content is not clipped */
}

p { overflow: hidden; /* content is not clipped */  }

p { overflow: scroll; /* always show scrollbars */  }

p { overflow: auto; /* append scrollbars if necessary */  }
```

```html
<p>visible (default)
Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium.</p>
```

## Example: `overflow-x`

```css
#div1, #div2, #div3, #div4 {
  border: 1px solid black;
  width:  250px;
  margin-bottom: 12px;
}

#div1 { overflow-x: hidden;}
#div2 { overflow-x: scroll;}
#div3 { overflow-x: visible;}
#div4 { overflow-x: auto;}
```

```html
<ul>
  <li><code>overflow-x:hidden</code> — hides the text outside the box
    <div id="div1">
      ABCDEFGHIJKLMOPQRSTUVWXYZABCDEFGHIJKLMOPQRSTUVWXYZ
    </div>
  </li>

  <li><code>overflow-x:scroll</code> — always adds a scrollbar
    <div id="div2">
      ABCDEFGHIJKLMOPQRSTUVWXYZABCDEFGHIJKLMOPQRSTUVWXYZ
    </div>
  </li>

  <li><code>overflow-x:visible</code> — displays the text outside the box if needed
    <div id="div3">
      ABCDEFGHIJKLMOPQRSTUVWXYZABCDEFGHIJKLMOPQRSTUVWXYZ
    </div>
  </li>

  <li><code>overflow-x:auto</code> — on most browsers, equivalent to <code>scroll</code>
    <div id="div4">
      ABCDEFGHIJKLMOPQRSTUVWXYZABCDEFGHIJKLMOPQRSTUVWXYZ
    </div>
  </li>
</ul>
```

## Example: `overflow-y`

```css
#div1,
#div2,
#div3 {
  border: 10px dotted blue;
  width:  200px;
  height: 100px;
}

#div1 { overflow-y: visible; }
#div2 { overflow-y: auto; }
#div3 { overflow-y: hidden; }
```

```html
<div id="div1">
  <h1><code>overflow-y:visible;</code></h1>
  <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.</p>
</div>

<div id="div2">
  <h1><code>overflow-y:auto;</code></h1>
  <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.</p>
</div>

<div id="div3">
  <h1><code>overflow-y:hidden;</code></h1>
  <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.</p>
</div>
```

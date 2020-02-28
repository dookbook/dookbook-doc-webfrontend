TOPICS: height property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Property: `height`

The **`height`** CSS property specifies the **height of an element**. By default, the property defines
the **height of the content area**. If **`box-sizing`** is set to **`border-box`**, however, it
instead determines **the height of the border area**.

## Property Value

| Property Value | Description |
| :--- | :--- |
| length | Defines the height as an absolute value. |
| **`%`** | Defines the height as a percentage of the containing block's height. |
| **`auto`** | The browser will calculate and select a height for the specified element. |

## Examples

```html
<div id="taller">I'm 50 pixels tall.</div>
<div id="shorter">I'm 25 pixels tall.</div>
<div id="parent">
  <div id="child">
    I'm half the height of my parent.
  </div>
</div>
```

```css
div {
  width: 250px;
  margin-bottom: 5px;
  border: 2px solid blue;
}

#taller {
  height: 50px;
}

#shorter {
  height: 25px;
}

#parent {
  height: 100px;
}

#child {
  height: 50%;
  width: 75%;
}
```

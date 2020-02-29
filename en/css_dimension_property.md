TOPICS: CSS Dimension
        width property
        min-width property
        max-width property
        height property
        min-height property
        max-height property

# CSS Dimension

The **CSS Dimension** property allows you to control the **height** and **width** of an element.

## CSS Property: `width`

The **`width`** CSS property sets **an element's width**. By default, it sets the width of the
content area, but if **`box-sizing`** is set to **`border-box`**, it sets **the width of the border area**.

| Property Value | Description |
| :--- | :--- |
| length | Use **`px`**, **`rem`**, **`em`** and other units to define the width |
| **`%`** | Defines the percentage width based on the width of the containing block (parent element) |
| **`auto`** | The browser will calculate and select a width for the specified element. |
| **`inherit`** | Specifies that the value of the `width` property should be inherited from the parent element |

```css
p.goldie {
  background: gold;
}
```

```html
<p class="goldie">The Mozilla community produces a lot of great software.</p>
```

## CSS Property: `min-width`

The **`min-width`** CSS property sets **the minimum width of an element**. It prevents the used
value of the [*`width`*](/en/webfrontend/width) property from becoming smaller than the value
specified for `min-width`.

| Property Value | Description |
| :--- | :--- |
| length | Defines the `min-width` as an absolute value. |
| **`%`** | Defines the min-width as a percentage of the containing block's width. |

Examples

```css
p {
  min-width:150px;
  background-color:yellow;
  width: 10px
}
```

```html
<!-- The minimum width of this paragraph is set to 150px -->
<p>min-width</p>
```

## CSS Property: `max-width`

The **`max-width`** CSS property sets **the maximum width of an element**. It prevents the used
value of the [**`width`**](/en/webfrontend/width) property from becoming larger than the value
specified by `max-width`.

| Property Value | Description |
| :--- | :--- |
| length | Defines the height as an absolute value. |
| **`%`** | Defines the height as a percentage of the containing block's height. |
| **`auto`** | The browser will calculate and select a height for the specified element. |

Examples

In this example, the `"child"` will be either `150` pixels wide or the width of the `"parent"`,
whichever is smaller:

```html
<div id="parent">
  <div id="child">
    Fusce pulvinar vestibulum eros, sed luctus ex lobortis quis.
  </div>
</div>
```

```css
#parent {
  background: lightblue;
  width: 300px;
}

#child {
  background: gold;
  width: 100%;
  max-width: 150px;
}
```

## CSS Property: `height`

The **`height`** CSS property specifies the **height of an element**. By default, the property defines
the **height of the content area**. If **`box-sizing`** is set to **`border-box`**, however, it
instead determines **the height of the border area**.

| Property Value | Description |
| :--- | :--- |
| length | Defines the height as an absolute value. |
| **`%`** | Defines the height as a percentage of the containing block's height. |
| **`auto`** | The browser will calculate and select a height for the specified element. |

Examples

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

## CSS Property: `min-height`

The **`min-height`** CSS property sets **the minimum height of an element**. It prevents the used value
of the [**`height`**](/en/webfrontend/height_property) property from becoming smaller than the value
specified for `min-height`.

| Property Value | Description |
| :--- | :--- |
| length | Defines the `min-height` as an absolute value. |
| **`%`** | Defines the `min-height` as a percentage of the containing block's height. |

Examples

```css
p {
  min-height:100px;
  background-color:yellow;
}
```

```html
<p>The minimum height of this paragraph is set to 100 px.</p>
```

## CSS Property: `max-height`

The **`max-height`** CSS property sets **the maximum height of an element**. It prevents the used
value of the [**`height`**](/en/webfrontend/height) property from becoming larger than the value
specified for `max-height`.

| Property Value | Description |
| :--- | :--- |
| length | Defines the `max-height` as an absolute value. |
| **`%`** | Defines the `max-height` as a percentage of the containing block's height. |

Examples

```html
<p>The maximum height of this segment is set to 50 px. The maximum height of this segment is set to 50 px. The maximum height of this segment is set to 50 px. The maximum height of this segment is set to 50 px. The maximum height of this segment is set to 50 px. The maximum height of this segment is set to 50 px. The maximum height of this segment is set to 50 px. The maximum height of this segment is set to 50 px. The maximum height of this segment is set to 50 px. The maximum height of this segment is set to 50 px.</p>
```

```css
p{
  max-height:50px;
  background-color:yellow;
}
```

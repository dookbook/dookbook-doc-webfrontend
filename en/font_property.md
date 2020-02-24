TOPICS: font property
        font-style property
        font-variant property
        font-weight property
        font-size property
        font-family property

# CSS Property: `font`

The **`font`** CSS property is a shorthand for **`font-style`**, **`font-variant`**,
**`font-weight`**, **`font-size`**, **`line-height`**, and **`font-family`**.
Alternatively, it sets an element's font to a system font.

## CSS Property: `font-style`

The **`font-style`** CSS property sets whether a font should be styled with a normal, italic, or
oblique face from its `font-family`.

| Property Value | Description |
| :--- | :--- |
| **`normal`** | Select the regular font of `font-family`.|
| **`italic`** | Select italic. If no italic version is available for the current font, oblique will be used instead. |
| **`oblique`** | Select italic. If no italic version is available for the current font, italic will be used instead. |

## CSS Property: `font-variant`

**`font-variant`** Property settings **Small capital letters display text**, which means that all
lower case letters will be converted to upper case, but all letters using small capital letters
will be compared to the rest of the text With a smaller font size

| Property Value | Description |
| :--- | :--- |
| **`normal`** | Defaults. The browser displays a standard font. |
| **`small-caps`** | The browser displays the font of small capital letters. |
| **`inherit`** | Specifies that the value of the `font-variant` attribute should be inherited from the parent element |

## CSS Property: `font-weight`

The **`font-weight`** CSS property sets the **weight (or boldness) of the font**. The weights available
depend on the `font-family` you are using.

| Property Value | Description |
| :--- | :--- |
| **`bold`** | Bold. Equivalent to **`700`**. |
| **`normal`** | Normal thickness. Equivalent to **`400`**.|
| **`100`**, **`200`**, **`300`**, **`400`**, **`500`**, **`600`**, **`700`**, **`800`**, **`900`** | A numerical way to specify the font thickness provides more values than **`normal`** and **`bold`**.|
| **`lighter`** | Define finer characters. |
| **`bolder`** | Defines thicker characters. |

## CSS Property: `font-size`

The **`font-size`** CSS property sets the **size of the font**. This property is also used to compute
the size of `em`, `ex`, and other relative `<length>` units.

| Property Value | Description |
| :--- | :--- |
| **`xx-small`**,**`x-small`**,**`small`**,**`medium`**,**`large`**,**`x-large`**,**`xx-large`** | Set the font size to different sizes, from **`xx-small`** to **`xx-large`**. <br> Default: **`medium`**.|
| **`smaller`** | Set to a smaller size than the parent element.|
| **`larger`** | Set to a larger size than the parent element. |
| length | Set to a fixed value. |
| **`%`** | Set to a percentage value based on the parent element. |
| **`inherit`** | Specifies that the font size should be inherited from the parent element.|

## CSS Property: `font-family`

The **`font-family`** CSS property specifies a prioritized list of one or more **font family names**
and/or **generic family names** for the selected element.

| Property Value | Description |
| :--- | :--- |
| family-name, generic-family | A prioritized list of font family names and / or class family names for an element. <br> Default: Browser-dependent |
| **`inherit`** | Specifies that the font family should be inherited from the parent element |

## Examples: Use `font` property

```css
p.ex1 {
  font: 15px arial, sans-serif;
}

p.ex2 {
  font: italic bold 12px/30px Georgia, serif;
}
```

```html
<p class="ex1">This is a paragraph. This is a paragraph. This is a paragraph. This is a paragraph. This is a paragraph. This is a paragraph. This is a paragraph. This is a paragraph.</p>
<p class="ex2">This is a paragraph. This is a paragraph. This is a paragraph. This is a paragraph. This is a paragraph. This is a paragraph. This is a paragraph. This is a paragraph.</p>
```

## Examples: Use `font-style` property

```css
.normal {
  font-style: normal;
}

.italic {
  font-style: italic;
}

.oblique {
  font-style: oblique;
}
```

## Examples: Use `font-variant` property

```css
p.normal { font-variant: normal; }
p.small { font-variant: small-caps; }
```

```html
<p class="normal">My name is Hege Refsnes.</p>
<p class="small">My name is Hege Refsnes.</p>
```

## Examples: Use `font-weight` property

```css
/* Set paragraph text to be bold. */
p {
  font-weight: bold;
}

/* Set div text to two steps darker than
   normal but less than a standard bold. */
div {
  font-weight: 600;
}

/* Sets text enclosed within span tag
   to be one step lighter than the parent. */
span {
  font-weight: lighter;
}
```

```html
<p>
  Alice was beginning to get very tired of sitting by her sister on the
  bank, and of having nothing to do: once or twice she had peeped into the
  book her sister was reading, but it had no pictures or conversations in
  it, 'and what is the use of a book,' thought Alice 'without pictures or
  conversations?'
</p>

<div>I'm heavy<br/>
  <span>I'm lighter</span>
</div>
```

## Examples: Use `font-size` property

```css
h1 { font-size: 250%; }
h2 { font-size: 200%; }
p { font-size: 100%; }
```

```html
<h1>This is heading 1</h1>
<h2>This is heading 2</h2>
<p>This is a paragraph.</p>
```

## Examples: Use `font-family` property

```css
p.serif { font-family: "Times New Roman", Times, serif; }
p.sansserif { font-family: Arial, Helvetica, sans-serif; }
```

```html
<h1>CSS font-family</h1>
<p class="serif">The font of this paragraph is Times New Roman </p>
<p class="sansserif">The font of this paragraph is Arial.</p>
```

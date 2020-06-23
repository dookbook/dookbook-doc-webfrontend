TOPICS: tab-size property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Property: `tab-size`

CSS property **`tab-size`** is used to customize the **width** of the tab character (U+0009).

## Property value

| Property Value | Description |
| :--- | :--- |
| **number** | The default value is `8`. Specifies the number of space characters to be displayed for each tab character. |
| **length** | Specifies the length of the tab character. Almost all major browsers do not support this property value. |

## Examples

```css
#t1{
  tab-size: 4;
}

#t2{
  tab-size: 16;
}
```

```html
<pre id="t1">
I use tab-size 4
</pre>

<pre id="t2">
I use tab-size 16
</pre>
```

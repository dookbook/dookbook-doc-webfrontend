TOPICS: text-transform property

# CSS Property: `text-transform`

The **`text-transform`** CSS property specifies **how to capitalize an element's text**. It can be used
to **make text appear in all-uppercase or all-lowercase**, or with each word capitalized. It also can
help improve legibility for ruby.

## Property Value

| Property Value | Description |
| :--- | :--- |
| **`none`** | Default. Defines standard text with lowercase and uppercase letters. |
| **`capitalize`** | Each word in the text begins with a capital letter. |
| **`uppercase`** | Text capital letters. |
| **`lowercase`** | Text lowercase letters. |
| **`inherit`** | Specifies that the value of the `text-transform` attribute should be inherited from the parent element. |

## Examples

```css
p.uppercase { text-transform:uppercase; }
p.lowercase { text-transform:lowercase; }
p.capitalize { text-transform:capitalize; }
```

```html
<p class="uppercase">This is some text.</p>
<p class="lowercase">This is some text.</p>
<p class="capitalize">This is some text.</p>
```

TOPICS: hanging-punctuation property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Property: `hanging-punctuation`

The **`hanging-punctuation`** CSS property specifies
**whether a punctuation mark should hang at the start or end of a line of text**. Hanging punctuation
may be placed outside the line box.

Should punctuation be placed at the beginning or end of a text sentence

## Syntax

The `hanging-punctuation` property may be specified with **one**, **two**, or **three** values.

- **One-value** syntax uses any one of the keyword values in the list below.
- **Two-value** syntax uses one of the following:
    - **`first`** together with any one of **`last`**, **`allow-end`**, or **`force-end`**
    - **`last`** together with any one of **`first`**, **`allow-end`**, or **`force-end`**
- **Three-value** syntax uses one of the following:
    - **`first`**, **`allow-end`**, and **`last`**
    - **`first`**, **`force-end`**, and **`last`**

## Property Value

| Property Value | Description |
| :--- | :--- |
| **`none`** | No character hangs. |
| **`first`** | An opening bracket or quote at the start of the first formatted line of an element hangs. |
| **`last`** | A closing bracket or quote at the end of the last formatted line of an element hangs. |
| **`force-end`** | A stop or comma at the end of a line hangs. |
| **`allow-end`** | A stop or comma at the end of a line hangs if it does not otherwise fit prior to justification. |

## Examples

```css
p {
  hanging-punctuation: first last;
  margin: 0.5rem;
}
```

```html
<p>“Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur dignissim nunc mauris, et sollicitudin est scelerisque sed. Praesent laoreet tortor massa, sit amet vulputate nulla pharetra ut.”</p>
```

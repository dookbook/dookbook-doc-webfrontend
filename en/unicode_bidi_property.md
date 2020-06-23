TOPICS: unicode-bidi property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Property: `unicode-bidi`

The CSS **`unicode-bidi`** property and [**`direction`**](/en/webfrontend/direction_property) property
determine how to deal with **double writing direction text** in the document. For example: if a piece
of content contains both **left-to-right writing** and **right-to-left writing**, then the user agent
uses a complex `Unicode` algorithm to decide how to display the text. The `unicode-bidi` property
overrides this algorithm, allowing developers to control text embedding.

**`unicode-bidi`** and [**`direction`**](/en/webfrontend/direction_property) are the only two not
[**`all`**](/en/webfrontend/all_property) Shorthand affected properties.

## Property value

| Property Value | Description |
| :--- | :--- |
| **`normal`** | For bidirectional algorithms, this element does not provide an additional level of embedding. For inline elements, implicit reordering works on element boundaries. |
| **`embed`** | For inline elements, this value opens an additional level of embedding for bidirectional algorithms. The direction of the embedding level is given by the [*`direction`*](/en/webfrontend/direction_property) property. |
| **`bidi-override`** | For inline elements, this value creates an override; for block container elements, this value creates an override for inline-level descendants that are not within another block container element. This means that within the element, according to the [*`direction`*](/en/webfrontend/direction_property) property, the reordering is strictly in order; the implicit part of the bidirectional algorithm is ignored. |
| **`isolate`** | This keyword indicates that when calculating the direction of an element container, the content of this element is not considered. Therefore, this element is separated from its siblings. When applying its two-way resolution algorithm, its container element treats it as one or more U+FFFC Object Replacement Character, that is, like `image`. |
| **`isolate-override`** | This keyword applies the isolation behavior of the **`isolate`** keyword to the surrounding content, and applies the override behavior of the **`bidi-override`** keyword to the internal content. |
| **`plaintext`** | This keyword does not consider the bidirectional state of the parent element or the value of the [*`direction`*](/en/webfrontend/direction_property) property when calculating the direction of the element. It is calculated using the P2 and P3 rules of the `Unicode` bidirectional algorithm. This value allows displaying formatted data according to the `Unicode` bidirectional algorithm.|

## Examples

```css
.bible-quote {
  direction: rtl;
  unicode-bidi: embed;
}
```

```html
<div class="bible-quote">
  A line of text
</div>
<div>
  Another line of text
</div>
```

TOPICS: <pre>

# HTML Preformatted Element: `<pre>`

The **HTML `<pre>` element** represents **preformatted text** which is to be presented exactly as
written in the HTML file. The text is typically rendered using a non-proportional ("*monospace*")
font. *Whitespace* (eg,. `Space` and `Tab`) inside this element is displayed as written.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *palpable content*. |
| **Permitted content** | *Phrasing content*. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *flow content*. |
| **Permitted ARIA roles** | Any |
| **DOM interface** | **`HTMLPreElement`** |

## Attributes

This element only includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| ~~`wrap`~~ | A hint indicating how the overflow must happen. In modern browser this hint is ignored and no visual effect results in its present; to achieve such an effect, use CSS **`white-space`** instead. |

## Simple Example

```html
<p>Using CSS to change the font color is easy.</p>
<pre>
body {
  color: red;
}
</pre>
```

## HTML Code in `<pre>`

```html
<pre>
&lt;html&gt;  <!-- Note the use of symbol entities to escape -->
</pre>
```

If you wish to use the `<pre>` tag to define **computer source code**, use it in conjunction with
the **[`<code>`](/en/webfrontend/<code>)** element to get more precise semantics.

```html
<pre><code>
&lt;html&gt;  <!-- Note the use of symbol entities to escape -->
</code></pre>
```

## Accessibility Concerns

It is important to provide an alternate description for any images or diagrams created using
preformatted text. The alternate description should clearly and concisely describe
the image or diagram's content.

People experiencing low vision conditions and browsing with the aid of assistive technology such as
a screen reader may not understand what the preformatted text characters are
representing when they are read out in sequence.

A combination of the [`<figure>`](/en/webfrontend/<figure>) and [`<figcaption>`](/en/webfrontend/<figcaption>)
elements, supplemented by a
combination of an `id` and the ARIA `role` and `aria-labelledby` attributes allow the
preformatted text to be announced as an image, with the `figcaption`
serving as the image's alternate description.

```html
<figure role="img" aria-labelledby="cow-caption">
  <pre>
  ___________________________
< I'm an expert in my field. >
  ---------------------------
         \   ^__^
          \  (oo)\_______
             (__)\       )\/\
                 ||----w |
                 ||     ||
  </pre>
  <figcaption id="cow-caption">
    A cow saying, "I'm an expert in my field." The cow is illustrated using preformatted
    text characters.
  </figcaption>
</figure>
```

- [MDN Understanding WCAG, Guideline 1.1 explanations](https://wiki.developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#Guideline_1.1_%E2%80%94_Providing_text_alternatives_for_non-text_content)
- [H86: Providing text alternatives for ASCII art, emoticons, and leetspeak | W3C Techniques for WCAG 2.0](https://www.w3.org/TR/WCAG20-TECHS/H86.html)

## Browser compatibility

| - | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
| `<pre>` | support | support | support |

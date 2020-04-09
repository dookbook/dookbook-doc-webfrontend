TOPICS: content property
        counter-increment property
        counter-reset property

# CSS Insert Content Property: `content`

The **`content`** CSS property of CSS is used for [`::before`](/en/webfrontend/::before) and [`::after`](/en/webfrontend/::after)
**Insert content** in pseudo elements. The content inserted using the `content` attribute are
anonymous replaceable elements.

## Property Value

| Property Value | Description |
| :--- | :--- |
| **`none`** | empty |
| **`normal`** | Normal, the default is `none` |
| **`counter`** | Set counter content |
| **`attr(attribute)`** | As one of the attributes of the selector |
| **`string`** | Set Content to the text you specified |
| **`open-quote`** | Open quotes |
| **`close-quote`** | Closing quotes |
| **`no-open-quote`** | If specified, remove the opening quotation marks of the content |
| **`no-close-quote`** | If specified, remove the closing quotation marks of the content |
| **url(url)** | URL address of media (image, sound, video, etc.) |
| **`inherit`** | Inherit from parent element |

## CSS Property: `counter-increment`

**`counter-increment`** property **increment one** or **multiple counter values**. It is commonly
used for the *`counter-reset`* property and *`content`* property.

| Property Value | Description |
| :--- | :--- |
| **`none`** | No counter will be incremented |
| **custom-ident** | Name of the **counter to increment** |
| **integer** | **counter value**. If not, the default is `1` |

## CSS Property: `counter-reset`

**`counter-reset`** property **create** or **reset a** or **multiple counters**. This is usually used
with *`counter-increment`*, *`content`*.

| Property Value | Description |
| :--- | :--- |
| **`none`** | The default. The selector counter cannot be reset |
| **custom-ident** | The name of the counter to reset |
| **integer** | The value to which the counter is reset each time an element appears. If not specified, the default is `0` |

## Simple Example

```html
<h1>5</h1>
<p> We shall start this with a quote from Sir Tim Berners-Lee,
    <q cite="http://www.w3.org/People/Berners-Lee/FAQ.html#Internet">
        I was lucky enough to invent the Web at the time when the Internet already existed - and had for a decade and a half.</q>  We must understand that there is nothing fundamentally wrong with building on the contributions of others.
</p>

<h1>6</h1>
<p> Here we shall quote the Mozilla Manifesto,
    <q cite="http://www.mozilla.org/en-US/about/manifesto/">
        Individuals must have the ability to shape the Internet and their own experiences on the Internet.</q> And so, we can infer that contributing to the open web, can protect our own individual experiences on it.
</p>
```

```css
q {
  color: #00008b;
  font-style: italic;
}

q::before { content: open-quote; }
q::after { content: close-quote; }

h1::before { content: "Chapter "; }
```

## Example: Use `counter-increment` and `counter-reset` attributes

```html
<body>
  <h1>HTML tutorials</h1>
  <h2>HTML Tutorial</h2>
  <h2>XHTML Tutorial</h2>
  <h2>CSS Tutorial</h2>

  <h1>Scripting tutorials</h1>
  <h2>JavaScript</h2>
  <h2>VBScript</h2>

  <h1>XML tutorials</h1>
  <h2>XML</h2>
  <h2>XSL</h2>
</body>
```

```css
body { counter-reset: section; }

h1 { counter-reset: subsection; }

h1:before {
  counter-increment: section;
  content: "Section " counter(section) ". ";
}

h2:before {
  counter-increment: subsection;
  content: counter(section) "." counter(subsection) " ";
}
```

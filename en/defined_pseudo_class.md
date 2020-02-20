TOPICS: :defined
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Pseudo-Class: `:defined`

The **`:defined`** CSS pseudo-class represents any element that has been defined. This includes any
standard element built in to the browser, and custom elements that have been successfully defined
(i.e. with the `CustomElementRegistry.define()` method).

## Example

The following snippets are taken from our defined-pseudo-class demo (see it live also).

In this demo we define a very simple trivial custom element:

```javascript
customElements.define('simple-custom',
  class extends HTMLElement {
    constructor() {
      super();

      let divElem = document.createElement('div');
      divElem.textContent = this.getAttribute('text');

      let shadowRoot = this.attachShadow({mode: 'open'})
        .appendChild(divElem);
  }
})
```

Then insert a copy of this element into the document, along with a standard [`<p>`](/en/webfrontend/<p>):

```html
<simple-custom text="Custom element example text"></simple-custom>

<p>Standard paragraph example text</p>
```

In the CSS we first include the following rules:

```css
// Give the two elements distinctive backgrounds
p {
  background: yellow;
}

simple-custom {
  background: cyan;
}

// Both the custom and the built-in element are given italic text
:defined {
  font-style: italic;
}
```

Then provide the following two rules to hide any instances of our custom element that are not defined,
and display instances that are defined as block level elements:

```css
simple-custom:not(:defined) {
  display: none;
}

simple-custom:defined {
  display: block;
}
```

This is useful if you have a complex custom element that takes a while to load into the page — you
might want to hide instances of the element until definition is complete, so that you don't end up
with flashes of ugly unstyled elements on the page

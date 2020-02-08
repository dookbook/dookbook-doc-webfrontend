TOPICS: <dfn>

# HTML Definition Element: `<dfn>`

The **HTML Definition element** (**`<dfn>`**) is used to indicate the **term** being defined within the
context of a **definition** phrase or sentence.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*, *palpable content*.|
| **Permitted content** | *Phrasing content*, but no `<dfn>` element must be a descendant. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *phrasing content*. |
| **Permitted ARIA roles** | Any |
| **DOM interface** | **`HTMLElement`** |

## Attributes

This element's attributes include the [global attributes](/en/webfrontend/HTML_Global_Attributes).

## Usage Notes

### Specifying the Term being Defined

The term being defined is identified following these rules:

- If the `<dfn>` element has a **`title`** attribute, the value of the `title` attribute is considered
to be the term being defined. The element must still have text within it, but that text may be an
abbreviation (perhaps using *[`<abbr>`](/en/webfrontend/<abbr>)*) or another form of the term.
- If the `<dfn>` contains **a single child element** and does not have any text content of its own,
and the child element is an **[`<abbr>`](/en/webfrontend/<abbr>)** element with a `title` attribute
itself, then the exact value of the [`<abbr>`](/en/webfrontend/<abbr>) element's `title` is the
term being defined.
- Otherwise, the text content of the `<dfn>` element is the term being defined.

!!! warn "`<dfn>` element has a `title` attribute"
    If the `<dfn>` element has a `title` attribute, it must contain the term being
    defined and no other text.

### Links to `<dfn>` elements

If you include an **`id`** attribute on the `<dfn>` element, you can then link to it using
*[`<a>`](/en/webfrontend/<a>)* elements. Such links should be uses of the term, with the
intent being that the reader can quickly navigate to the term's definition if they're not
already aware of it, by clicking on the term's link.

### Definition of the Term

The [`<p>`](/en/webfrontend/<p>) element, the [`<dt>`](/en/webfrontend/<dt>)
[`<dd>`](/en/webfrontend/<dd>) pairing, or the [`<section>`](/en/webfrontend/<section>)
element which is the nearest ancestor of the `<dfn>` is considered to be the definition of the term.

## Examples

Let's take a look at some examples of various usage scenarios.

### Basic identification of a term

This example simply uses a plain `<dfn>` element to identify the location of a term within the definition.

```html
<p>The <strong>HTML Definition element</strong>
(<strong><dfn>&lt;dfn&gt;</dfn></strong>) is used to indicate the
term being defined within the context of a definition phrase or
sentence.</p>
```

Since the `<dfn>` element has no `title`, the text contents of the `<dfn>` element itself are used
as the term being defined.

### Links to definitions

To add links to the definitions, you create the link the same way you always do,
with the [`<a>`](/en/webfrontend/<a>) element.

```html
<p>The <strong>HTML Definition element</strong>
(<strong><dfn id="definition-dfn">&lt;dfn&gt;</dfn></strong>) is
used to indicate the term being defined within the context of a
definition phrase or sentence.</p>

<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Graece
donan, Latine voluptatem vocant. Confecta res esset. Duo Reges:
constructio interrete. Scrupulum, inquam, abeunti; </p>

<p>Negare non possum. Dat enim intervalla et relaxat. Quonam modo?
Equidem e Cn. Quid de Pythagora? In schola desinis. </p>

<p>Ubi ut eam caperet aut quando? Cur iustitia laudatur? Aperiendum
est igitur, quid sit voluptas; Quid enim? Non est igitur voluptas
bonum. Urgent tamen et nihil remittunt. Quid enim possumus hoc
agere divinius? </p>

<p>Because of all of that, we decided to use the
<code><a href="#definition-dfn">&lt;dfn&gt;</a></code> element for
this project.</p>
```

Here we see the definition — now with an *`id`* attribute, `"definition-dfn"`, which can be
used as the target of a link. Later on, a link is created using [`<a>`](/en/webfrontend/<a>)
with the `href` attribute set to `"#definition-dfn"` to set up the link back to the definition.

### Using abbreviations and definitions together

In some cases, you may wish to use an abbreviation for a term when defining it. This can be done by
using the `<dfn>` and *[`<abbr>`](/en/webfrontend/<abbr>)* elements in tandem, like this:

```html
<p>The <dfn><abbr title="Hubble Space Telescope">HST</abbr></dfn>
is among the most productive scientific instruments ever constructed.
It has been in orbit for over 20 years, scanning the sky and
returning data and photographs of unprecedented quality and
detail.</p>

<p>Indeed, the <abbr title="Hubble Space Telescope">HST</abbr> has
arguably done more to advance science than any device ever built.</p>
```

Note the [`<abbr>`](/en/webfrontend/<abbr>) element nested inside the `<dfn>`. The former
establishes that the term is an abbreviation ("HST") and specifies the full term
("Hubble Space Telescope") in its `title` attribute. The latter indicates that the abbreviated term
represents a term being defined.

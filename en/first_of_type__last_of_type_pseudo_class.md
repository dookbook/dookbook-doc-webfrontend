TOPICS: :first-of-type
        :last-of-type
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Pseudo-Class: `:first-of-type`、`:last-of-type`

The **`:first-of-type`** CSS pseudo-class represents the first element of its type among a group of
sibling elements.

The **`:last-of-type`** CSS pseudo-class represents the last element of its type among a group of
sibling elements.

## Example: Decorate the first and last paragraphs

```html
<h2>Heading</h2>
<p>Paragraph 1</p>
<p>Paragraph 2</p>
<p>Paragraph 3</p>
<p>Paragraph 4</p>
```

```css
p:first-of-type {
  color: red;
  font-style: italic;
}

p:last-of-type {
  color: blue;
  font-style: italic;
}
```

## Example: Nested elements

```html
<article>
  <div>This `div` is first!</div>
  <div>This <span>nested `span` is first</span>!</div>
  <div>This <em>nested `em` is first</em>, but this <em>nested `em` is last</em>!</div>
  <div>This <span>nested `span` gets styled</span>!</div>
  <b>This `b` qualifies!</b>
  <div>This is the final `div`.</div>
</article>
```

```css
article :first-of-type {
  background-color: pink;
}

article :last-of-type {
  background-color: red;
}
```

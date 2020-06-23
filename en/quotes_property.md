TOPICS: quotes property

# CSS Property: `quotes`

The CSS **quotes`** property is used to set the style of **quotation marks**.

## Property value

| Property Value | Description |
| :--- | :--- |
| **`none`** | [**`content`**](/en/webfrontend/content_property) The value of the property *`open-quote`* and *`close-quote`* will not display quotation marks. |
| **"string" "string"** | Define the **quotation marks to be used**. <br>The first two values specify the first level of reference nesting, and the last two values specify the next level of quote nesting.|

## Examples

```html
<q>To be or not to be. That's the question!</q>
```

```css
q {
  quotes: '"' '"' "'" "'";
}
q::before {
  content: open-quote;
}
q:after {
  content: close-quote;
}
```

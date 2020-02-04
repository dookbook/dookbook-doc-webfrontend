TOPICS: onscroll
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `onscroll`

The **onscroll** property of the `GlobalEventHandlers` mixin is an `EventHandler` that processes
`scroll` events.

The `scroll` event fires when the document view or an element has been scrolled, whether by the user,
a Web API, or the user agent.

!!! warn "Note"
    Don't confuse `onscroll` with `onwheel`: `onwheel` handles general wheel rotation, while
    `onscroll` handles scrolling of an object's content.

## Syntax

```javascript
target.onscroll = functionRef;
```

`functionRef` is a function name or a function expression. The function receives a `UIEvent`
object as its sole argument.

Only one `onscroll` handler can be assigned to an object at a time. For greater flexibility, you can
pass a `scroll` event to the `EventTarget.addEventListener()` method instead.

## Example

This example monitors scrolling on a `<textarea>`, and logs the element's vertical scroll position accordingly.

```html
<textarea>1 2 3 4 5 6 7 8 9</textarea>
<p id="log"></p>
```

此示例监视`<textarea>`上的滚动，并相应记录元素的垂直滚动位置。

```html
<textarea>1 2 3 4 5 6 7 8 9</textarea>
<p id="log"></p>
```

```css
textarea {
  width: 4rem;
  height: 8rem;
  font-size: 3rem;
}
```

```javascript
const textarea = document.querySelector('textarea');
const log = document.getElementById('log');

textarea.onscroll = logScroll;

function logScroll(e) {
  log.textContent = `Scroll position: ${e.target.scrollTop}`;
}
```

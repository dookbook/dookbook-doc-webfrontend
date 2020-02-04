TOPICS: onmousemove
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `onmousemove`

The **`onmousemove`** property of the `GlobalEventHandlers` mixin is an `EventHandler` that
processes mousemove events.

The `mousemove` event fires when the user moves the mouse.

## Syntax

```javascript
target.onmousemove = functionRef;
```

`functionRef` is a function name or a function expression. The function receives a
`MouseEvent` object as its sole argument.

## Examples

This example creates link tooltips that follow your mouse. It uses the `onmousemove`, `onmouseover`,
and `onmouseout` event handlers.

```html
<p><a href="#" data-tooltip="First link">See a tooltip here &hellip;</a></p>
<p><a href="#" data-tooltip="Second link">&hellip; or here!</a></p>
```

```css
.tooltip {
  position: absolute;
  z-index: 9999;
  padding: 6px;
  background: #ffd;
  border: 1px #886 solid;
  border-radius: 5px;
}
```

```javascript
const tooltip = new (function() {
  const node = document.createElement('div');
  node.className = 'tooltip';
  node.setAttribute('hidden', '');
  document.body.appendChild(node);

  this.follow = function(event) {
    node.style.left = event.clientX + 20 + 'px';
    node.style.top = event.clientY + 10 + 'px';
  };

  this.show = function(event) {
    node.textContent = event.target.dataset.tooltip;
    node.removeAttribute('hidden');
  };

  this.hide = function() {
    node.setAttribute('hidden', '');
  };
})();

const links = document.querySelectorAll('a');

links.forEach(link => {
  link.onmouseover = tooltip.show;
  link.onmousemove = tooltip.follow;
  link.onmouseout = tooltip.hide;
});
```

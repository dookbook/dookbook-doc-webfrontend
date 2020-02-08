TOPICS: oncontextmenu
        contextmenu
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `contextmenu` Event

The **`oncontextmenu`** property of the `GlobalEventHandlers` mixin is an `EventHandler` that
processes **`contextmenu`** events.

The `contextmenu` event typically fires when the right mouse button is clicked on the window. Unless
the default behavior is prevented, the browser context menu will activate.

## Syntax

```javascript
target.oncontextmenu = functionRef;
```

`functionRef` is a function name or a function expression. The function receives an `Event` object
as its sole argument.

Only one `oncontextmenu` handler can be assigned to an object at a time. You may prefer to use the
`EventTarget.addEventListener()` method instead, since it's more flexible.

## Example

### Disabling context menus

This snippet prevents context menus from opening in the window. The context menu typically
appears upon a right click.

```html
<p>Try opening the context menu. Is it disabled?<p>
```

```javascript
window.oncontextmenu = (e) => {
  e.preventDefault();
}
```

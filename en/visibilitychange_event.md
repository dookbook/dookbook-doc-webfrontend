TOPICS: onvisibilitychange
        visibilitychange
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `visibilitychange` Event

The **`Document.onvisibilitychange`** property represents the event handler that is called when a
**`visibilitychange`** event reaches this object.

## Syntax

```javascript
obj.onvisibilitychange = function;
```

`function` is the name of a user-defined function, without the `()` suffix or any parameters, or an
anonymous function declaration.

## Example

```javascript
document.onvisibilitychange = function() {
  console.log("Visibility of page has changed!");
};
```

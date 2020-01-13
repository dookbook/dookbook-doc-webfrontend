TOPICS: Element.hasAttributes

# `Element.hasAttributes()`

元素接口的 **`hasAttributes()`** 方法返回一个[`Boolean`](/en/webfrontend/Boolean），指示当前元素是否具有任何属性。

## Syntax

```javascript
var result = element.hasAttributes();
```

| 参数 | 说明 |
| :-- | :-- |
| `result` | 保留返回值`true`或`false`. |

## Examples

```javascript
let foo = document.getElementById('foo');
if (foo.hasAttributes()) {
  // Do something with 'foo.attributes'
}
```

## Polyfill

```javascript
;(function(prototype) {
  prototype.hasAttributes = prototype.hasAttributes || function() {
    return (this.attributes.length > 0);
  }
})(Element.prototype);
```

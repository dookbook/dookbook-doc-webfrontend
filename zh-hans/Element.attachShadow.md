TOPICS: Element.attachShadow
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.attachShadow()`

**`Element.attachShadow()`** 方法给指定的元素挂载一个Shadow DOM，并且返回它的 ShadowRoot.

## 语法

```javascript
var shadowroot = element.attachShadow(shadowRootInit);
```

| 参数 | 说明 |
| :-- | :-- |
| `shadowRootInit` | 一个`shadowRootInit`字典，包括下列字段：<br>`mode`: 一个指定Shadow DOM封装模式的字符串，可以是下列之一：<br>1. `open` 指定为开放的封装模式。<br>2. `closed` 指定为关闭的封装模式。

**返回值**: 返回一个 `ShadowRoot`.

## Examples

您可以看到我们在代码中间使用了`attachShadow()`来创建影子根，然后将自定义元素的内容附加到该根。

```javascript
// Create a class for the element
class WordCount extends HTMLParagraphElement {
  constructor() {
    // Always call super first in constructor
    super();

    // count words in element's parent element
    var wcParent = this.parentNode;

    function countWords(node){
      var text = node.innerText || node.textContent
      return text.trim().split(/\s+/g).length;
    }

    var count = 'Words: ' + countWords(wcParent);

    // Create a shadow root
    var shadow = this.attachShadow({mode: 'open'});

    // Create text node and add word count to it
    var text = document.createElement('span');
    text.textContent = count;

    // Append it to the shadow root
    shadow.appendChild(text);

    // Update count when element content changes
    setInterval(function() {
      var count = 'Words: ' + countWords(wcParent);
      text.textContent = count;
    }, 200)
  }
}

// Define the new element
customElements.define('word-count', WordCount, { extends: 'p' });
```

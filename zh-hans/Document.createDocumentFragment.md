TOPICS: Document.createDocumentFragment
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.createDocumentFragment()`

创建一个新的空白的文档片段(`DocumentFragment`)。

## 语法

```javascript
let fragment = document.createDocumentFragment();
```

`fragment` 是一个指向空`DocumentFragment`对象的引用。

## 描述

`DocumentFragments` 是DOM节点。它们不是主DOM树的一部分。通常的用例是创建文档片段，将元素附加到文档片段，然后将文档片段附加到DOM树。在DOM树中，文档片段被其所有的子元素所代替。

因为文档片段存在于内存中，并不在DOM树中，所以将子元素插入到文档片段时不会引起页面回流（对元素位置和几何上的计算）。因此，使用文档片段通常会带来更好的性能。

## 示例

```html
<ul id="ul">
</ul>
```

```javascript
var element  = document.getElementById('ul'); // assuming ul exists
var fragment = document.createDocumentFragment();
var browsers = ['Firefox', 'Chrome', 'Opera',
    'Safari', 'Internet Explorer'];

browsers.forEach(function(browser) {
  var li = document.createElement('li');
  li.textContent = browser;
  fragment.appendChild(li);
});

element.appendChild(fragment);
```

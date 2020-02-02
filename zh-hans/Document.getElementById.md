TOPICS: Document.getElementById
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.getElementById()`

`Document`的方法 **`getElementById()`** 返回一个匹配特定 ID的元素. 由于元素的 ID 在大部分情况下要求是独一无二的，这个方法自然而然地成为了一个高效查找特定元素的方法。

如果需要查找到那些没有ID 的元素，你可以考虑通过CSS选择器使用 [`querySelector()`](/zh-hans/webfrontend/document.querySelector)。

## 语法

```javascript
node = document.adoptNode(externalNode);
```

| 参数 | 说明 |
| :-- | :-- |
| `element` | 是一个 `Element` 对象。如果当前文档中拥有特定ID的元素不存在则返回`null`. |
| `id` | 是大小写敏感的字符串，代表了所要查找的元素的唯一ID. |

**返回值**: 返回一个匹配到 ID 的 DOM `Element` 对象。若在当前 `Document` 下没有找到，则返回 `null`。

## 示例

```html
<!DOCTYPE html>
<html>
<head>
  <title>getElementById example</title>
</head>
<body>
  <p id="para">Some text here</p>
  <button onclick="changeColor('blue');">blue</button>
  <button onclick="changeColor('red');">red</button>
</body>
</html>
```

```javascript
function changeColor(newColor) {
​  var elem = document.getElementById('para');
  elem.style.color = newColor;
}
```

## 注意

对 “Id” 的拼写一定要正确。无论看起来多么合情合理，`getElementByID()` 都是不合理的且永远都不会工作的。

不同于其他 Element 查找方法（如[`Document.querySelector()`](/zh-hans/webfrontend/document.querySelector) 以及
[`Document.querySelectorAll()`](/zh-hans/webfrontend/document.querySelectorAll)），`getElementById()`
只有在作为 `document` 的方法时才能起作用，而在DOM中的其他元素下无法生效。这是因为 ID 值在整个网页中必须保持唯一。因此没有必要为这个方法创建所谓的 “局部” 版本。

```html
<!doctype html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
  <div id="parent-id">
    <p>hello word1</p>
    <p id="test1">hello word2</p>
    <p>hello word3</p>
    <p>hello word4</p>
  </div>
  <script>
    var parentDOM = document.getElementById('parent-id');
    var test1=parentDOM.getElementById('test1');
    //抛出错误
    //（这是一条错误信息）Uncaught TypeError: parentDOM.getElementById is not a function
  </script>
</body>
</html>
```

如果没有查找到对应的元素，方法会返回`null`。注意ID参数是大小写敏感的，所以`document.getElementById("Main")`无法获取到元素`<div id="main">`，因为'M'和'm'是不一样的。

`getElementById`方法不会搜索**不在文档中的元素**。当创建一个元素，并且分配ID后，你必须要使用`insertBefore`或其他类似的方法把元素插入到文档中，
之后才能使用 `getElementById` 获取到:

```javascript
var element = document.createElement("div");
element.id = 'testqq';
var el = document.getElementById('testqq'); // el 是个 null
```

非HTML文档（Non-HTML documents）。 DOM的实现必须说明哪个属性是ID类型。只有DTD定义了'id'是ID属性时’id‘才会被认为是ID属性。在 XHTML 或者其他文档中，'id'通常被定义为ID类型的属性。不知道哪个属性是ID类型的实现中，这会返回null结果。

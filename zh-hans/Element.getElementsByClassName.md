TOPICS: Element.getElementsByClassName
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.getElementsByClassName()`

**`Element.getElementsByClassName()`** 方法返回一个即时更新的（live） `HTMLCollection`，包含了所有拥有指定 `class` 的子元素。
当在 `document` 对象上调用此方法时，会检索整个文档，包括根元素。

相似地，`getElementsByClassName()` 方法会在整个文档上执行；它返回指定拥有指定 `class` 名称的 `document` 根节点的后代元素。

## 语法

```javascript
var elements = element.getElementsByClassName(names);
```

- `elements` 是一个即时更新的（live）`HTMLCollection`。
- `names` 是一个字符串，表示要匹配的类名（class names）列表；类名被空白符分隔。
- `element` 是文档中的任一 `Element`。

## 示例

获取所有包含`class`名称为 `test` 的元素：

```javascript
element.getElementsByClassName('test');
```

获取所有包含 `red` 和 `test` `class`名的元素：

```javascript
element.getElementsByClassName('red test');
```

获取 `id` 为 `main` 的元素的所有包含一个 `test` `class`名的后代元素：

```javascript
document.getElementById('main').getElementsByClassName('test');
```

可以在任何 `HTMLCollection` 上面使用 `Array.prototype` 的方法，要把 `HTMLCollection` 作为该方法的上下文对象（this）。下例，
查找类名为 `test` 的元素中的所有 `<div>` 元素：

```javascript
var testElements = document.getElementsByClassName('test');
var testDivs = Array.prototype.filter.call(testElements, function(testElement){
    return testElement.nodeName === 'div';
});
```

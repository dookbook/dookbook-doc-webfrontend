TOPICS: Document.getElementsByName
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.getElementsByName()`

根据给定的 `name` 返回一个在 (X)HTML `document`的节点列表集合。

## 语法

```javascript
elements = document.getElementsByName(name)
```

- `elements` 是一个实时更新的 `NodeList` 集合。

| 参数 | 说明 |
| :-- | :-- |
| `name` | 是元素的 `name` 属性的值。 |

## 示例

```html
<!DOCTYPE html>
<html lang="en">
<head>
 ...
</head>

<body>
<form name="up"><input type="text"></form>
<div name="down"><input type="text"></div>

<script>
var up_forms = document.getElementsByName("up");
console.log(up_forms[0].tagName); // returns "FORM"
</script>
</body>
</html>
```

## 注释

`name` 属性只有在(X)HTML文档中可用。

该方法返回一个live的 `NodeList` 集合，这个集合包含 name 属性为指定值的所有元素，例如[`<meta>`](/zh-hans/webfrontend/<meta>) 、
[`<object>`](/zh-hans/webfrontend/<object>)，甚至那些不支持 `name` 属性但是添加了 `name` 自定义属性的元素也包含其中。

!!! error ""
    `getElementsByName`  在不同的浏览器其中工作方式不同。在IE和Opera中， `getElementsByName()` 方法还会返回那些 id 为指定值的元素。
    所以你要小心使用该方法，最好不要为元素的 `name` 和 `id` 赋予相同的值。

!!! error ""
    IE 和 Edge 都返回一个 `HTMLCollection`, 而不是`NodeList` 。

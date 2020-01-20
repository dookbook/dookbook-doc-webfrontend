TOPICS: Document.createRange
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.createRange()`

返回一个 `Range` 对象。

## 语法

```javascript
range = document.createRange();
```

- `range` 是一个 `Range` 对象。

## 示例

```javascript
var range = document.createRange();

range.setStart(startNode, startOffset);
range.setEnd(endNode, endOffset);
```

## 注意

一旦一个 `Range` 对象被建立，在使用他的大多数方法之前需要去设置他的临界点。

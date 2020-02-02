TOPICS: Document.hasStorageAccess

# `Document.hasStorageAccess()`

`Document`接口的 **hasStorageAccess()** 方法返回一个`Promise`，该`Promise`使用布尔值解析，该布尔值指示文档是否有权访问其第一方存储。

## 语法

```javascript
Promise<boolean> hasStorageAccess()
```

**参数**: 没有参数

## 返回值

一个以布尔值解析的`Promise`，该布尔值指示文档是否有权访问其第一方存储。

如果在最初调用该函数时已解决了承诺，并且正在处理用户手势事件，则解析处理程序将像正在处理用户手势一样运行，因此它将能够调用需要用户激活的API。

## 示例

```javascript
document.hasStorageAccess().then(hasAccess => {
  if (hasAccess) {
    // storage access has been granted already.
  } else {
    // storage access hasn't been granted already;
    // you may want to call requestStorageAccess().
  }
});
```

## 技术指标

该API目前仅处于提案阶段-标准化过程尚未开始。 当前，您可以在Apple的Storage Access API简介博客文章中找到该API的规范详细信息，以及WHATWG HTML第3338号-建议：
Storage Access API。

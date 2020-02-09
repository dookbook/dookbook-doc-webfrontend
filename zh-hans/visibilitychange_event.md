TOPICS: onvisibilitychange
        visibilitychange

# `visibilitychange` 事件

`Document.onvisibilitychange` 是一个事件处理方法，它将在该对象的 **`visibilitychange`** 事件被触发时调用。

## 语法

```javascript
obj.onvisibilitychange = function;
```

`function` 是一个用户定义的方法的名字（而非带`()`和任何参数的函数调用），或者匿名函数的申明。

## 示例

```javascript
document.onvisibilitychange = function() {
  console.log("Visibility of page has changed!");
};
```

TOPICS: String.valueOf
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.valueOf()`

**`valueOf()`** 方法返回一个[`String`](/zh-hans/webfrontend/String)对象的原始值（primitive value）。

## 语法

```javascript
str.valueOf()
```

**参数**: 没有参数

**返回值**: 一个字符串代表着给定 `String` 对象的初始值。

## 描述

[`String`](/zh-hans/webfrontend/String) 对象的 `valueOf` 方法返回一个[`String`](/zh-hans/webfrontend/String)对象的原始值。该值等同于[`String.toString()`](/zh-hans/webfrontend/String.toString)。

该方法通常在 JavaScript 内部被调用，而不是在代码里显式调用。

## 示例

### 使用 `valueOf()`

```javascript
x = new String("Hello world");
console.log(x.valueOf())          // Displays "Hello world"
```

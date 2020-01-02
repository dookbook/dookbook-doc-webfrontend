TOPICS: String.[@@iterator]
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.[@@iterator]()`

**`[@@iterator]()`** 方法返回一个新的`Iterator`对象，它遍历字符串的代码点，返回每一个代码点的字符串值。

该交互式示例的源存储在GitHub存储库中。 如果您想为交互式示例项目做出贡献，请克隆[https://github.com/mdn/interactive-examples](https://github.com/mdn/interactive-examples)并向我们发送请求请求。

## 语法

```javascript
string[Symbol.iterator]
```

**参数**: 没有参数

**返回值**: 一个新的`Iterator`对象。

## 示例

### 使用 `[@@iterator]()`

```javascript
var string = 'A\uD835\uDC68';

var strIter = string[Symbol.iterator]();

console.log(strIter.next().value); // "A"
console.log(strIter.next().value); // "\uD835\uDC68"
```

### 通过 `for..of` 使用`[@@iterator]()`

```javascript
var string = 'A\uD835\uDC68B\uD835\uDC69C\uD835\uDC6A';

for (var v of string) {
  console.log(v);
}
// "A"
// "\uD835\uDC68"
// "B"
// "\uD835\uDC69"
// "C"
// "\uD835\uDC6A"
```

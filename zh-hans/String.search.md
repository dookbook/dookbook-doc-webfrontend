TOPICS: String.search
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.search()`

**`search()`** 方法执行正则表达式和 [`String`](/zh-hans/webfrontend/String) 对象之间的一个搜索匹配。

## 语法

```javascript
str.search(regexp)
```

| 参数 | 说明 |
| :-- | :-- |
| `regexp` | 一个正则表达式（regular expression）对象。如果传入一个非正则表达式对象 `obj`，则会使用 `new RegExp(obj)` 隐式地将其转换为正则表达式对象。 |

**返回值**: 如果匹配成功，则 `search()` 返回正则表达式在字符串中首次匹配项的索引;否则，返回 `-1`。

## 描述

当你想要知道字符串中是否存在某个模式（`pattern`）时可使用 `search()`，类似于正则表达式的 `test()` 方法。当要了解更多匹配信息时，可使用 [`match()`](/zh-hans/webfrontend/String.match)
（但会更慢一些），该方法类似于正则表达式的 `exec()` 方法。

## 示例

### 使用 `search()`

下面的例子中用两个不同的正则表达式对同一个字符串执行搜索匹配，得到一个成功匹配（正数返回值）和一个失败匹配（`-1`）。

```javascript
var str = "hey JudE";
var re = /[A-Z]/g;
var re2 = /[.]/g;
console.log(str.search(re)); // returns 4, which is the index of the first capital letter "J"
console.log(str.search(re2)); // returns -1 cannot find '.' dot punctuation
```

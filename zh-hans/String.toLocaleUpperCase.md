TOPICS: String.toLocaleUpperCase
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.toLocaleUpperCase()`

**`toLocaleUpperCase()`** 使用本地化（locale-specific）的大小写映射规则将输入的字符串转化成大写形式并返回结果字符串。

## 语法

```javascript
str.toLocaleUpperCase()
str.toLocaleUpperCase(locale)
str.toLocaleUpperCase([locale, locale, ...])
```

| 参数 | 说明 |
| :-- | :-- |
| `locale` 可选 | `locale` 参数指明要转换成大写格式的特定语言区域。如果以一个 Array形式给出多个`locales`参数，最佳语言区域将被应用（ 参考[best available locale](https://tc39.github.io/ecma402/#sec-bestavailablelocale) ）。 默认的`locale`是主机环境的当前区域(`locale`)设置。|

**返回值**: 一个新的字符串，即根据本地化的大小写映射规则将输入的字符串转化成大写形式的结果。

### 例外情况

- 如果语言环境参数不是有效的语言标签，则会抛出`RangeError`（"无效的语言标签：xx_yy"）。
- 如果数组元素不是字符串类型，则抛出`TypeError`（"语言环境参数中的无效元素"）。

## 描述

`toLocaleUpperCase()` 方法返回的是将输入的字符串根据本地化的大小写映射规则转化成的大写形式的新字符串。`toLocaleUpperCase()` 不会影响输入的字符串本身的值.
大多数情况下，这个方法与 [`toUpperCase()`](/zh-hans/webfrontend/String.toUpperCase) 会产生相同的值，但是对于一些语言（`locale`）,例如土耳其语，因为它们的大小写映射规则与Unicode默认的映射规则不同，所以调用这两个方法将会产生不同的结果。

## 示例

### 使用 `toLocaleUpperCase()`

```javascript
'alphabet'.toLocaleUpperCase(); // 'ALPHABET'

'Gesäß'.toLocaleUpperCase(); // 'GESÄSS'

'i\u0307'.toLocaleUpperCase('lt-LT'); // 'I'

let locales = ['lt', 'LT', 'lt-LT', 'lt-u-co-phonebk', 'lt-x-lietuva'];
'i\u0307'.toLocaleUpperCase(locales); // 'I'
```

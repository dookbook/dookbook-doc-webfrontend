TOPICS: Infinity
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# JavaScript `Infinity` Object

全局属性 `Infinity` 是一个数值，表示无穷大。

| Infinity 性质属性 |  |
| :-- | :-- |
|**`writable`**|`false`|
|**`enumerable`**|`false`|
|**`configurable`**|`false`|

```JavaScript
const maxNumber = Math.pow(10, 1000); // max positive number

if (maxNumber === Infinity) {
  console.log("Let's call it Infinity!");
  // expected output: "Let's call it Infinity!"
}

console.log(1 / maxNumber);
// expected output: 0
```

## 描述

`Infinity` 是全局对象（global object）的一个属性，即它是一个全局变量。

`Infinity` 的初始值是 [`Number.POSITIVE_INFINITY`](/zh-hans/webfrontend/Number.POSITIVE_INFINITY)。Infinity（正无穷大）大于任何值。
该值和数学意义上的无穷大很像，例如任何正值乘以 `Infinity` 为 `Infinity`, 任何数值（除了`Infinity` 和 `-Infinity`）除以 `Infinity` 为 `0`。

在 ECMAScript 5 的规范中， `Infinity` 是只读的（实现于 JavaScript 1.8.5 / Firefox 4）。

## 示例

```JavaScript
console.log(Infinity          ); /* Infinity */  
console.log(Infinity + 1      ); /* Infinity */  
console.log(Math.pow(10, 1000)); /* Infinity */  
console.log(Math.log(0)       ); /* -Infinity */  
console.log(1 / Infinity      ); /* 0 */
```

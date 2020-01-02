TOPICS: Generator
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# JavaScript `Generator` Object

**生成器**对象是由一个 [`generator function`](/zh-hans/webfrontend/function) 返回的，并且它符合[可迭代协议](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#iterable)和[迭代器协议](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#iterable)。

## 语法

```JavaScript
function* gen() {
  yield 1;
  yield 2;
  yield 3;
}

let g = gen();
// "Generator { }"
```

## 方法

| 方法 | 说明 |
| :-- | :-- |
|**[`Generator.next()`](/zh-hans/webfrontend/Generator.next)**|返回一个由  [`yield`](/zh-hans/webfrontend/yield)](/zh-hans/webfrontend/yield) 表达式生成的值。|
|**[`Generator.return()`](/zh-hans/webfrontend/Generator.return)**|返回给定的值并结束生成器。|
|**[`Generator.throw()`](/zh-hans/webfrontend/Generator.throw)**|向生成器抛出一个错误。|

## 示例

### 一个无限迭代器

```JavaScript
function* idMaker(){
    let index = 0;
    while(true)
        yield index++;
}

let gen = idMaker(); // "Generator { }"

console.log(gen.next().value);
// 0
console.log(gen.next().value);
// 1
console.log(gen.next().value);
// 2
// ...
```

## 传统的生成器对象

Firefox (SpiderMonkey) 在 *JavaScript 1.7* 中也实现了一个较早版本的生成器，其中函数声明中的星号（*）不是必需的
(只需在函数体中使用 [`yield`](/zh-hans/webfrontend/yield) 关键字)。
但是，旧式生成器已弃用。不要使用它们;他们将被删除 *(bug 1083482)*。

### 传统的生成器方法

| 方法 | 说明 |
| :-- | :-- |
|**`Generator.next()`**|返回 [`yield`](/zh-hans/webfrontend/yield) 表达式产生的值. 与 ES2015 生成器对象的`next()`方法对应.*(此API尚未标准化)*|
|**`Generator.close()`**|关闭生成器，因此执行该函数后调用`next()`函数时将会抛出 `StopIteration` 错误. 与 ES2015 生成器对象的`return()`方法对应.*(此API尚未标准化)*|
|**`Generator.send()`**|用于将值发送到生成器。 该值由 [`yield`](/zh-hans/webfrontend/yield) 表达式返回, 并且返回下一个 [`yield`](/zh-hans/webfrontend/yield) 表达式产生的值. `send(x)` 对应于ES2015生成器对象中的 `next(x)`.*(此API尚未标准化)*|
|**`Generator.throw()`**|向生成器抛出错误. 与 ES2015 生成器对象的`throw()`方法对应.*(此API尚未标准化)*|

### 旧生成器对象示例

```JavaScript
function fibonacci() {
  var a = yield 1;
  yield a * 2;
}

var it = fibonacci();
console.log(it);          // "Generator {  }"
console.log(it.next());   // 1
console.log(it.send(10)); // 20
console.log(it.close());  // undefined
console.log(it.next());   // throws StopIteration (as the generator is now closed)
```

TOPICS: EvalError
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# JavaScript `EvalError` Object

`EvalError` 代表了一个关于 `eval` 函数的错误。此异常不再会被JavaScript抛出，但是`EvalError`对象仍然保持兼容性。

## 语法

```JavaScript
new EvalError([message[, fileName[, lineNumber]]])
```

### 参数

| 参数 | 说明 |
| :-- | :-- |
|**`message`**|可选参数。人类可阅读的关于错误的描述。|
|**`fileName`**|*(非标准)*|可选参数。代码中导致异常的文件的文件名。|
|**`lineNumber`**|*(非标准)*|可选参数。代码中导致异常的代码的行号。|

## 属性

| 属性 | 说明 |
| :-- | :-- |
|**`EvalError.prototype`**|允许向`EvalError`对象中添加自定义属性。|

## 方法

全局的`EvalError`对象本身不包含任何方法, 然而它通过原型链继承了一些方法。

## EvalError 实例

### 实例属性

| 属性 | 说明 |
| :-- | :-- |
|**`EvalError.prototype.constructor`**|指定创建实例原型的函数。|
|**[`EvalError.message`](/zh-hans/webfrontend/EvalError.message)**|错误信息。 从 ECMA-262 开始 [`EvalError`](/zh-hans/webfrontend/EvalError) 提供 `message` （继承自[`Error.message`](/zh-hans/webfrontend/Error..message)）属性, 详见 [SpiderMonkey](https://developer.mozilla.org/en-US/docs/Mozilla/Projects/SpiderMonkey)。|
|**[`EvalError.name`](/zh-hans/webfrontend/EvalError.name)**|错误名称。继承自 [`Error`](/zh-hans/webfronted/Error)。|
|**[`EvalError.fileName`](/zh-hans/webfrontend/EvalError.fileName)**|引发错误的文件路径。 继承自 [`Error`](/zh-hans/webfronted/Error)。|
|**[`EvalError.lineNumber`](/zh-hans/webfrontend/EvalError.lineNumber)**|引发错误所在行。继承自 [`Error`](/zh-hans/webfronted/Error)。|
|**[`EvalError.columnNumber`](/zh-hans/webfrontend/EvalError.columnNumber)**|引发错误所在的列。 继承自 [`Error`](/zh-hans/webfronted/Error)。|
|**[`EvalError.stack`](/zh-hans/webfrontend/EvalError.stack)**|堆栈。继承自 [`Error`](/zh-hans/webfronted/Error)。|

### 实例方法

虽然 `EvalError` 自己的属性方法较少, 但是通过原型链继承了很多有用的方法。

## 示例

`EvalError` 不在当前ECMAScript规范中使用，因此不会被运行时抛出。但是对象本身仍然与规范的早期版本向后兼容。

### 创建 EvalError

```JavaScript
try {
  throw new EvalError('Hello', 'someFile.js', 10);
} catch (e) {
  console.log(e instanceof EvalError); // true
  console.log(e.message);              // "Hello"
  console.log(e.name);                 // "EvalError"
  console.log(e.fileName);             // "someFile.js"
  console.log(e.lineNumber);           // 10
  console.log(e.columnNumber);         // 0
  console.log(e.stack);                // "@Scratchpad/2:2:9\n"
}
```

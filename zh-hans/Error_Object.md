TOPICS: Error
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# JavaScript `Error` Object

通过`Error`的构造器可以创建一个错误对象。当运行时错误产生时，`Error`的实例对象会被抛出。`Error`对象也可用于用户自定义的异常的基础对象。下面列出了各种内建的标准错误类型。

## 语法

```JavaScript
new Error([message[, fileName[,lineNumber]]])
```

### 参数

| 参数| 说明 |
| :-- | :-- |
|**`message`**|人类可阅读的错误描述信息。|
|**`fileName`** *(可选)*| 可选。被创建的`Error`对象的`fileName`属性值。默认是调用`Error`构造器代码所在的文件的名字。 *(此API尚未标准化)*|
|**`lineNumber Optional`** *(可选)*| 被创建的`Error`对象的`lineNumber`属性值。默认是调用`Error`构造器代码所在的文件的行号。*(此API尚未标准化)*|

## 描述

当代码运行时的发生错误，会创建新的 `Error` 对象，并将其抛出。

该页面描述了 `Error` 对象自身的使用,以及其构造函数的使用. 关于 `Error` 实例的内部属性和方法,请看 `Error.prototype`。

### 作为函数使用

当像函数一样使用 `Error` 时 -- 如果没有 [`new`](/zh-hans/webfrontend/new)，它将返回一个 `Error` 对象。
所以， 仅仅调用 `Error` 将产生与通过 `new` 关键字构造 `Error` 对象的输出相同。

```JavaScript
// this:
const x = Error('I was created using a function call!');
​​​​// has the same functionality as this:
const y = new Error('I was constructed via the "new" keyword!');
```

### Error 类型

除了通用的`Error`构造函数外，JavaScript还有6个其他类型的错误构造函数。更多客户端异常,详见 [Exception Handling Statements](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Control_flow_and_error_handling)。

| Error 类型 | 说明 |
| :-- | :-- |
|**[`EvalError`](/zh-hans/webfrontend/EvalError)**|创建一个`Error`实例，表示错误的原因：与 [`eval()`](/zh-hans/webfrontend/eval) 有关。 |
|**[`InternalError`](/zh-hans/webfrontend/InternalError)**|创建一个代表JavaScript引擎内部错误的异常抛出的实例。 如: `"递归太多"`。|
|**[`RangeError`](/zh-hans/webfrontend/RangeError)**|创建一个`Error`实例，表示错误的原因：数值变量或参数超出其有效范围。|
|**[`ReferenceError`](/zh-hans/webfrontend/ReferenceError)**|创建一个`Error`实例，表示错误的原因：无效引用。|
|**[`SyntaxError`](/zh-hans/webfrontend/SyntaxError)**|创建一个`Error`实例，表示错误的原因：[`eval()`](/zh-hans/webfrontend/eval)在解析代码的过程中发生的语法错误。|
|**[`TypeError`](/zh-hans/webfrontend/TypeError)**|创建一个`Error`实例，表示错误的原因：变量或参数不属于有效类型。|
|**[`URIError`](/zh-hans/webfrontend/URIError)**|创建一个`Error`实例，表示错误的原因：给 [`encodeURI()`](/zh-hans/webfrontend/encodeURI) 或 [`decodeURI()`](zh-hansn/webfrontend/decodeURI) 传递的参数无效。|

## 属性

| 属性 | 说明 |
| :-- | :-- |
|**`Error.prototype`**|允许添加属性到`Error`实例。|

## 方法

全局`Error`对象自身不包含任何方法,但从原型链中继承了一些方法。

## Error 实例

所有`Error`实例和非通用错误的实例都继承自`Error.prototype`。 与所有构造函数一样，可以使用构造函数的原型向使用该构造函数创建的所有实例添加属性或方法。

### 标准属性

| 属性 | 说明 |
| :-- | :-- |
|**`Error.prototype.constructor`**|定义创建实例原型的函数。|
|**[`Error.message`](/zh-hans/webfrontend/Error.message)**|错误信息.|
|**[`Error.name`](/zh-hans/webfrontend/Error.name)**|错误名称.|

### 供应商特定的扩展

!!! warn "非标准"
    此功能是非标准的。 请勿在面向Web的生产环境中使用它：它不适用于每个用户。 操作实现之间也可能存在很大的不兼容性，并且将来的行为可能会更改。

(1) Microsoft

| Microsoft 属性 | 说明 |
| :-- | :-- |
|**[`Error.description`](/zh-hans/webfrontend/Error.description)**|错误描述,类似于错误信息。|
|**[`Error.number`](/zh-hans/webfrontend/Error.number)**|错误编号。|

(2) Mozilla

| Mozilla 属性 | 说明 |
| :-- | :-- |
|**[`Error.fileName`](/zh-hans/webfrontend/Error.fileName)**|引发此错误的文件的路径。|
|**[`Error.lineNumber`](/zh-hans/webfrontend/Error.lineNumber)**|文件中引起此错误的行号。|
|**[`Error.columnNumber`](/zh-hans/webfrontend/Error.columnNumber)**|引发此错误的行中的列号。|
|**[`Error.stack`](/zh-hans/webfrontend/Error.stack)**|堆栈跟踪。|

### 实例方法

| 方法 | 说明 |
| :-- | :-- |
|**[`Error.toSource()`](/zh-hans/webfrontend/Error.toSource)**|返回一个字符串，其中包含指定的“Error”对象的来源；可以使用此值创建一个新对象。 覆盖 [`Object.toSource()`](/zh-hans/webfrontend/Object.toSource) 方法。|
|**[`Error.toString()`](/zh-hans/webfrontend/Error.toString)**|返回表示指定对象的字符串。 覆盖 [`Object.toString()`](zh-hansn/webfrontend/Object.toString) 方法。|

## 示例

### 抛出一个基本错误

通常你会使用[`throw`](/zh-hans/webfrontend/throw)关键字来抛出你创建的`Error`对象。
可以使用 [`try...catch`](/zh-hans/webfrontend/try...catch) 结构来处理异常:

```JavaScript
try {
  throw new Error('Whoops!');
} catch (e) {
  console.error(e.name + ': ' + e.message);
}
```

### 处理一个特定错误

你可以通过判断异常的类型来特定处理某一类的异常,即判断 [`constructor`](/zh-hans/webfrontend/Object.constructor) 属性，
当使用现代JavaScript引擎时,可使用 [`instanceof`](/zh-hans/webfrontend/instanceof) 关键字：

```JavaScript
try {
  foo.bar();
} catch (e) {
  if (e instanceof EvalError) {
    console.error(e.name + ': ' + e.message);
  } else if (e instanceof RangeError) {
    console.error(e.name + ': ' + e.message);
  }
  // ... etc
}
```

### 自定义异常类型

你可能希望自定义基于`Error`的异常类型，使得你能够 `throw new MyError()` 并可以使用 `instanceof MyError` 来检查某个异常的类型. 这种需求的通用解决方法如下.

!!! warn "注意"
    在FireFox中抛出自定义类型的异常会显示不正确的行号和文件名。

参考 ["What's a good way to extend Error in JavaScript?"](https://stackoverflow.com/questions/1382107/whats-a-good-way-to-extend-error-in-javascript)
discussion on Stackoverflow.

（1）ES6自定义错误类别

!!! warn ""
    Babel7之前的版本可以处理`CustomError`类方法，但只能在用[`Object.defineProperty()`](/zh-hans/webfrontend/Object.defineProperty)声明它们时使用。否则，Babel的旧版本和其他编译器在没有附加配置的情况下将无法正确处理以下代码。

!!! info ""
    使用ES2015类时，某些浏览器在堆栈跟踪中包含`CustomError`构造函数。

```JavaScript
class CustomError extends Error {
  constructor(foo = 'bar', ...params) {
    // Pass remaining arguments (including vendor specific ones) to parent constructor
    super(...params);

    // Maintains proper stack trace for where our error was thrown (only available on V8)
    if (Error.captureStackTrace) {
      Error.captureStackTrace(this, CustomError);
    }

    this.name = 'CustomError';
    // Custom debugging information
    this.foo = foo;
    this.date = new Date();
  }
}

try {
  throw new CustomError('baz', 'bazMessage');
} catch(e){
  console.error(e.name); //CustomError
  console.error(e.foo); //baz
  console.error(e.message); //bazMessage
  console.error(e.stack); //stacktrace
}
```

（2）ES5自定义错误对象

!!! warn ""
    使用原型声明时，所有浏览器都在堆栈跟踪中包括`CustomError`构造函数。

```JavaScript
function CustomError(foo, message, fileName, lineNumber) {
  var instance = new Error(message, fileName, lineNumber);
  instance.name = 'CustomError';
  instance.foo = foo;
  Object.setPrototypeOf(instance, Object.getPrototypeOf(this));
  if (Error.captureStackTrace) {
    Error.captureStackTrace(instance, CustomError);
  }
  return instance;
}

CustomError.prototype = Object.create(Error.prototype, {
  constructor: {
    value: Error,
    enumerable: false,
    writable: true,
    configurable: true
  }
});

if (Object.setPrototypeOf){
  Object.setPrototypeOf(CustomError, Error);
} else {
  CustomError.__proto__ = Error;
}

try {
  throw new CustomError('baz', 'bazMessage');
} catch(e){
  console.error(e.name); //CustomError
  console.error(e.foo); //baz
  console.error(e.message); //bazMessage
}
```

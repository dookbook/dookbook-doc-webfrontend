TOPICS:  AsyncFunction
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# JavaScript AsyncFunction Object

`AsyncFunction` 构造函数用来创建新的 [异步函数](/zh-hans/webfrontend/async_function) 对象，JavaScript 中每个异步函数都是  `AsyncFunction` 的对象。

注意，`AsyncFunction` 并不是一个全局对象，需要通过下面的方法来获取：
```
Object.getPrototypeOf(async function(){}).constructor
```


## 语法
```
new AsyncFunction([arg1[, arg2[, ...argN]],] functionBody)
```

### 参数
**`arg1, arg2, ... argN`**: 函数的参数名，它们是符合 JavaScript 标示符规范的一个或多个用逗号隔开的字符串。例如 `x`、`theValue`或 `a,b`。

**`functionBody`**: 一段字符串形式的 JavaScript 语句，这些语句组成了新函数的定义。


## 描述
执行 `AsyncFunction` 构造函数的时候，会创建一个 异步函数 对象。但是这种方式不如先用 异步函数表达式 定义一个异步函数，然后再调用其来创建 异步函数 对象来的高效，因为第二种方式中异步函数是与其他代码一起被解释器解析的，而第一种方式的函数体是单独解析的。

传递给 `AsyncFunction` 构造函数的所有参数，都会成为新函数中的变量，变量的名称和定义顺序与各参数相同。 

    !!!warn 注意：使用 `AsyncFunction` 构造函数创建的[[异步函数]] 并不会在当前上下文中创建闭包，其作用域始终是全局的。因此运行的时候只能访问它们自己的本地变量和全局变量，但不能访问构造函数被调用的那个作用域中的变量。这是它与 `eval` 不同的地方。

调用 `AsyncFunction` 构造函数时可以省略 [new](/zh-hans/webfrontend/new_operator)，其效果是一样的。


## 属性
**`AsyncFunction.length`**:  `AsyncFunction` 构造函数的 `length` 属性，值为`1`。

**`AsyncFunction.prototype`**: 通过原型对象可以为所有异步函数对象定义额外的属性。


## AsyncFunction 原型对象

### 属性
**`AsyncFunction.constructor`**:  默认值为 `AsyncFunction`。

**`AsyncFunction.prototype[@@toStringTag]`**: 返回 "AsyncFunction"。


## AsyncFunction 实例
`AsyncFunction` 实例继承了 `AsyncFunction.prototype` 的方法和属性。和所有构造函数一样，修改 `AsyncFunction` 构造函数的原型对象会同时对所有 `AsyncFunction` 实例上生效。


## 示例
### 通过 AsyncFunction 构造器创建一个异步函数
```
function resolveAfter2Seconds(x) {
  return new Promise(resolve => {
    setTimeout(() => {
      resolve(x);
    }, 2000);
  });
}

var AsyncFunction = Object.getPrototypeOf(async function(){}).constructor;
var a = new AsyncFunction('a', 
                          'b',
                          'return await resolveAfter2Seconds(a) + await resolveAfter2Seconds(b);');
a(10, 20).then(v => {
  console.log(v); // 4 秒后打印 30
});
```

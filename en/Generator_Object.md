TOPICS: Generator
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# JavaScript `Generator` Object

The **Generator** object is returned by a generator function and it conforms to both the
[iterable protocol](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols)
and the [iterator protocol](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols).

## Syntax

```JavaScript
function* gen() {
  yield 1;
  yield 2;
  yield 3;
}

var g = gen(); // "Generator { }"
```

## Methods

| Methods | Description |
| :-- | :-- |
|**[`Generator.next()`](/en/webfrontend/Generator.next)**|Returns a value yielded by the [`yield`](/en/webfrontend/yield) expression. |
|**[`Generator.return()`](/en/webfrontend/Generator.return)**|Returns the given value and finishes the generator.|
|**[`Generator.throw()`](/en/webfrontend/Generator.throw)**|Throws an error to a generator (also finishes the generator, unless caught from within that generator).|

## Example

### An infinite iterator

```JavaScript
function* idMaker() {
    var index = 0;
    while(true)
        yield index++;
}

var gen = idMaker(); // "Generator { }"

console.log(gen.next().value); // 0
console.log(gen.next().value); // 1
console.log(gen.next().value); // 2
// ...
```

## Legacy generator objects

Firefox (SpiderMonkey) also implemented an earlier version of generators in *JavaScript 1.7*,
where the star (*) in the function declaration was not necessary
(you just use the [`yield`](/en/webfrontend/yield) keyword in the function body). However,
legacy generators support has been removed since Firefox 58 (released on January 23, 2018) *(bug 1083482)*.

### Legacy generator methods

| methods | Description |
| :-- | :-- |
|**`Generator.next()`**|Returns a value yielded by the [`yield`](/en/webfrontend/yield) expression. This corresponds to `next()` in the ES2015 generator object.*(This API has not been standardied)*|
|**`Generator.close()`**|Closes the generator, so that when calling `next()` an `StopIteration` error will be thrown. This corresponds to the `return()` method in the ES2015 generator object.*(This API has not been standardied)*|
|**`Generator.send()`**|Used to send a value to a generator. The value is returned from the [`yield`](/en/webfrontend/yield) expression, and returns a value yielded by the next [`yield`](/en/webfrontend/yield) expression. `send(x)` corresponds to `next(x)` in the ES2015 generator object.*(This API has not been standardied)*|
|**`Generator.throw()`**|Throws an error to a generator. This corresponds to the `throw()` method in the ES2015 generator object.*(This API has not been standardied)*|

### Legacy generator example

```JavaScript
function* fibonacci() {
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

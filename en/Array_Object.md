TOPICS: Array
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# JavaScript `Array` Object

The JavaScript `Array` class is a global object that is used in the construction of arrays;
which are high-level, list-like objects.

## Description

Arrays are list-like objects whose prototype has methods to perform traversal and mutation operations.
Neither the length of a JavaScript array nor the types of its elements are fixed.
Since an array's length can change at any time, and data can be stored at non-contiguous locations
in the array, JavaScript arrays are not guaranteed to be dense;
this depends on how the programmer chooses to use them. In general, these are convenient characteristics;
 but if these features are not desirable for your particular use, you might consider using typed arrays.

Arrays cannot use strings as element indexes (as in an [associative array](/en/webfrontend/Associative_array))
 but must use integers. Setting or accessing via non-integers using
 [bracket notation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects#Objects_and_properties)
  (or [dot notation](https://wiki.developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Property_Accessors))
  will not set or retrieve an element from the array list itself, but will set or access a variable
  associated with that array's
  [object property collection](https://wiki.developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#Properties).
  The array's object properties and list of array elements are separate,
  and the array's traversal and mutation operations cannot be applied to these named properties.

## Common operations

### Create an Array

```JavaScript
var fruits = ['Apple', 'Banana'];

console.log(fruits.length);
//2
```

### Access (index into) an Array item

```JavaScript
var first = fruits[0];
// Apple

var last = fruits[fruits.length - 1];
// Banana
```

### Loop over an Array

```JavaScript
fruits.forEach(function(item, index, array) {
  console.log(item, index);
});
// Apple 0
// Banana 1
```

### Add to the end of an Array

```JavaScript
var newLength = fruits.push('Orange');
// ["Apple", "Banana", "Orange"]
```

### Remove from the end of an Array

```JavaScript
var last = fruits.pop(); // remove Orange (from the end)
// ["Apple", "Banana"];
```

### Remove from the front of an Array

```JavaScript
var first = fruits.shift(); // remove Apple from the front
// ["Banana"];
```

### Add to the front of an Array

```JavaScript
var newLength = fruits.unshift('Strawberry') // add to the front
// ["Strawberry", "Banana"];
```

### Find the index of an item in the Array

```JavaScript
fruits.push('Mango');
// ["Strawberry", "Banana", "Mango"]

var pos = fruits.indexOf('Banana');
// 1
```

### Remove an item by index position

```JavaScript
var removedItem = fruits.splice(pos, 1); // this is how to remove an item
// ["Strawberry", "Mango"]
```

### Remove items from an index position

```JavaScript
var vegetables = ['Cabbage', 'Turnip', 'Radish', 'Carrot'];
console.log(vegetables);
// ["Cabbage", "Turnip", "Radish", "Carrot"]

var pos = 1, n = 2;

var removedItems = vegetables.splice(pos, n);
// this is how to remove items, n defines the number of items to be removed,
// from that position(pos) onward to the end of array.

console.log(vegetables);
// ["Cabbage", "Carrot"] (the original array is changed)

console.log(removedItems);
// ["Turnip", "Radish"]
```

### Copy an Array

```JavaScript
var shallowCopy = fruits.slice(); // this is how to make a copy
// ["Strawberry", "Mango"]
```

## Syntax

```JavaScript
[element0, element1, ..., elementN]
new Array(element0, element1[, ...[, elementN]])
new Array(arrayLength)
```

### Parameters

| Parameters | Description |
| :-- | :-- |
|**`elementN`**| A JavaScript array is initialized with the given elements, except in the case where a single argument is passed to the Array constructor and that argument is a number (see the `arrayLength` parameter below). Note that this special case only applies to JavaScript arrays created with the Array constructor, not array literals created with the bracket syntax.|
|**`arrayLength`**| If the only argument passed to the Array constructor is an integer between `0` and `232-1` (inclusive), this returns a new JavaScript array with its `length` property set to that number (Note: this implies an array of `arrayLength` empty slots, not slots with actual `undefined` values). If the argument is any other number, a `RangeError` exception is thrown.|

### Accessing array elements

JavaScript arrays are zero-indexed: the first element of an array is at index `0`,
and the last element is at the index equal to the value ofthe array's [`length`](/en/webfrontend/Array.length)
 property minus `1`. Using an invalid index number returns `undefined`.

```JavaScript
var arr = ['this is the first element', 'this is the second element', 'this is the last element'];
console.log(arr[0]);              // logs 'this is the first element'
console.log(arr[1]);              // logs 'this is the second element'
console.log(arr[arr.length - 1]); // logs 'this is the last element'
```

Array elements are object properties in the same way that `toString` is a property,
but trying to access an element of an array as follows throws a syntax error
because the property name is not valid:

```JavaScript
console.log(arr.0); // a syntax error
```

There is nothing special about JavaScript arrays and the properties that cause this.
JavaScript properties that begin with a digit cannot be referenced with dot notation;
and must be accessed using bracket notation. For example,
if you had an object with a property named `'3d'`,
it can only be referenced using bracket notation. E.g.:

```JavaScript
var years = [1950, 1960, 1970, 1980, 1990, 2000, 2010];
console.log(years.0);   // a syntax error
console.log(years[0]);  // works properly
renderer.3d.setTexture(model, 'character.png');     // a syntax error
renderer['3d'].setTexture(model, 'character.png');  // works properly
```

Note that in the 3d example, `'3d'` had to be quoted.
It's possible to quote the JavaScript array indexes as well (e.g., `years['2']` instead of `years[2]`),
although it's not necessary. The `2` in `years[2]` is coerced into a string by the JavaScript engine
through an implicit `toString` conversion. It is, for this reason, that `'2'` and `'02'`
would refer to two different slots on the `years` object and the following example could be `true`:

```JavaScript
console.log(years['2'] != years['02']);
```

Similarly, object properties which happen to be reserved words(!) can only be accessed as string literals
 in bracket notation (but it can be accessed by dot notation in firefox 40.0a2 at least):

```JavaScript
var promise = {
  'var'  : 'text',
  'array': [1, 2, 3, 4]
};

console.log(promise['var']);
```

### Relationship between length and numerical properties

A JavaScript array's [`length`](/en/webfrontend/Array.length) property and numerical properties are connected.
Several of the built-in array methods (e.g., [`join()`](/en/webfrontend/Array.join),
[slice()](/en/webfrontend/Array.slice),
[`indexOf()`](/en/webfrontend/Array.indexOf), etc.)
take into account the value of an array's [`length`](/en/webfrontend/Array.length) property
when they're called. Other methods (e.g., [`push()`](/en/webfrontend/Array.push),
[`splice()`](/en/webfrontend/Array.splice), etc.)
 also result in updates to an array's [`length`](/en/webfrontend/Array.length) property.

```JavaScript
var fruits = [];
fruits.push('banana', 'apple', 'peach');

console.log(fruits.length); // 3
```

When setting a property on a JavaScript array when the property is a valid array index
and that index is outside the current bounds of the array,
the engine will update the array's [`length`](/en/webfrontend/Array.length) property accordingly:

```JavaScript
fruits[5] = 'mango';
console.log(fruits[5]); // 'mango'
console.log(Object.keys(fruits));  // ['0', '1', '2', '5']
console.log(fruits.length); // 6
```

Increasing the [`length`](/en/webfrontend/Array.length).

```JavaScript
fruits.length = 10;
console.log(Object.keys(fruits)); // ['0', '1', '2', '5']
console.log(fruits.length); // 10
```

Decreasing the [`length`](/en/webfrontend/Array.length) property does, however, delete elements.

```JavaScript
fruits.length = 2;
console.log(Object.keys(fruits)); // ['0', '1']
console.log(fruits.length); // 2
```

This is explained further on the [`Array.length`](/en/webfrontend/Array.length) page.

### Creating an array using the result of a match

The result of a match between a regular expression and a string can create a JavaScript array.
This array has properties and elements which provide information about the match.
Such an array is returned by [`RegExp.exec`](/en/webfrontend/RegExp.exec),
[`String.match`](/en/webfrontend/String.match),
and [`String.replace`](/en/webfrontend/String.replace).
To help explain these properties and elements,
look at the following example and then refer to the table below:

```JavaScript
// Match one d followed by one or more b's followed by one d
// Remember matched b's and the following d
// Ignore case

var myRe = /d(b+)(d)/i;
var myArray = myRe.exec('cdbBdbsbz');
```

The properties and elements returned from this match are as follows:

|Property/Element|Description|Example|
| :------------- | :--- | :--- |
|input|A read-only property that reflects the original string against which the regular expression was matched.|cdbBdbsbz|
|index|A read-only property that is the zero-based index of the match in the string.|1|
|[0]|A read-only element that specifies the last matched characters.|dbBd|
|[1], ...[n]|Read-only elements that specify the parenthesized substring matches, if included in the regular expression. The number of possible parenthesized substrings is unlimited.|[1]: bB [2]: d|

## Static properties

| properties | Description |
| :-- | :-- |
|**`Array.length`**| The `Array` constructor's `length` property whose value is `1`.|
|**[`get Array[@@species]`](/en/webfrontend/get_Array[@@species])**|The constructor function that is used to create derived objects.|
|**`Array.prototype`**| Array prototype object can add attributes to all array objects.|

## Static methods

| Static | Description |
| :-- | :-- |
|**[`Array.from()`](/en/webfrontend/Array.from)**| Creates a new Array instance from an array-like or iterable object.|
|**[`Array.isArray()`](/en/webfrontend/Array.isArray)**| Returns `true` if a variable is an array, if not false.|
|**[`Array.of()`](/en/webfrontend/Array.of)**| Creates a new Array instance with a variable number of arguments, regardless of number or type of the arguments.|

## Array instances

`Array` instances inherit from `Array.prototype`.

`Array.prototype` itself is an Array:

```JavaScript
Array.isArray(Array.prototype); // true
```

### Instance properties

| properties | Description |
| :-- | :-- |
|**`Array.prototype.constructor`**| Specifies the function that creates an object's prototype.|
|**[`Array.prototype.length`](/en/webfrontend/Array.length)**| Reflects the number of elements in an array.|
|**`Array.prototype[@@unscopables]`**| A symbol containing property names to exclude from a with binding scope.|

### Instance methods

**(1) Mutator methods**, These methods modify the array:

| methods | Description |
| :-- | :-- |
|**[`Array.copyWithin()`](/en/webfrontend/Array.copyWithin)**| Copies a sequence of array elements within the array.|
|**[`Array.fill()`](/en/webfrontend/Array.fill)**| Fills all the elements of an array from a start index to an end index with a static value.|
|**[`Array.pop()`](/en/webfrontend/Array.pop)**| Removes the last element from an array and returns that element.|
|**[`Array.push()`](/en/webfrontend/Array.push)**| Adds one or more elements to the end of an array and returns the new length of the array.|
|**[`Array.reverse()`](/en/webfrontend/Array.reverse)**| Reverses the order of the elements of an array in place — the first becomes the last, and the last becomes the first.|
|**[`Array.shift()`](/en/webfrontend/Array.shift)**| Removes the first element from an array and returns that element.|
|**[`Array.sort()`](/en/webfrontend/Array.sort)**| Sorts the elements of an array in place and returns the array.|
|**[`Array.splice()`](/en/webfrontend/Array.splice)**| Adds and/or removes elements from an array.|
|**[`Array.unshift()`](/en/webfrontend/Array.unshift)**| Adds one or more elements to the front of an array and returns the new length of the array.|

**(2) Accessor methods**,
These methods do not modify the array and return some representation of the array.

| methods | Description |
| :-- | :-- |
|**[`Array.concat()`](/en/webfrontend/Array.concat)**| Returns a new array that is this array joined with other array(s) and/or value(s).|
|**[`Array.includes()`](/en/webfrontend/Array.includes)**|Determines whether an array contains a certain element, returning true or false as appropriate.*(This is an experimental API that should not be used in production code)*|
|**[`Array.indexOf()`](/en/webfrontend/Array.indexOf)**|Returns the first (least) index of an element within the array equal to the specified value, or `-1` if none is found.|
|**[`Array.join()`](/en/webfrontend/Array.join)**| Joins all elements of an array into a string.|
|**[`Array.lastIndexOf()`](/en/webfrontend/Array.lastIndexOf)**| Returns the last (greatest) index of an element within the array equal to the specified value, or `-1` if none is found.|
|**[`Array.slice()`](/en/webfrontend/Array.slice)**| Extracts a section of an array and returns a new array.|
|**[`Array.toSource()`](/en/webfrontend/Array.toSource)**| Returns an array literal representing the specified array; you can use this value to create a new array. Overrides the [`Object.toSource()`](/en/webfrontend/Object.toSource) method.*(This API has not been standardized)*|
|**[`Array.toString()`](/en/webfrontend/Array.toString)**| Returns a string representing the array and its elements. Overrides the [`Object.toString()`](/en/webfrontend/Object.toString) method.|
|**[`Array.toLocaleString()`](/en/webfrontend/Array.toLocaleString)**| Returns a localized string representing the array and its elements. Overrides the [`Object.toLocaleString()`](/en/webfrontend/Object.toLocaleString) method.|

**(3) Iteration methods**,
Several methods take as arguments functions to be called back while processing the array.
 When these methods are called, the [`length`](/en/webfrontend/Array.length) of the array is sampled,
 and any element added beyond this length from within the callback is not visited.
 Other changes to the array (setting the value of or deleting an element) may affect the results of
 the operation if the method visits the changed element afterwards.
 While the specific behavior of these methods in such cases is well-defined,
 you should not rely upon it so as not to confuse others who might read your code.
 If you must mutate the array, copy into a new array instead.

| methods | Description |
| :-- | :-- |
|**[`Array.forEach()`](/en/webfrontend/Array.forEach)**|Calls a function for each element in the array.|
|**[`Array.entries()`](/en/webfrontend/Array.entries)**|Returns a new Array Iterator object that contains the key/value pairs for each index in the array.|
|**[`Array.every()`](/en/webfrontend/Array.every)**| Returns `true` if every element in this array satisfies the provided testing function.|
|**[`Array.filter()`](/en/webfrontend/Array.filter)**| Creates a new array with all of the elements of this array for which the provided filtering function returns `true`.|
|**[`Array.find()`](/en/webfrontend/Array.find)**| Returns the found value in the array, if an element in the array satisfies the provided testing function or `undefined` if not found.|
|**[`Array.findIndex()`](/en/webfrontend/Array.findIndex)**|Returns the found index in the array, if an element in the array satisfies the provided testing function or `-1` if not found.|
|**[`Array.keys()`](/en/webfrontend/Array.keys)**| Returns a new Array Iterator that contains the keys for each index in the array.|
|**[`Array.map()`](/en/webfrontend/Array.map)**| Creates a new array with the results of calling a provided function on every element in this array.|
|**[`Array.reduce()`](/en/webfrontend/Array.reduce)**| Apply a function against an accumulator and each value of the array (from left-to-right) as to reduce it to a single value.|
|**[`Array.reduceRight()`](/en/webfrontend/Array.reduceRight)**| Apply a function against an accumulator and each value of the array (from right-to-left) as to reduce it to a single value.|
|**[`Array.some()`](/en/webfrontend/Array.some)**| Returns true if at least one element in this array satisfies the provided testing function.|
|**[`Array.values()`](/en/webfrontend/Array.values)**| Returns a new Array Iterator object that contains the values for each index in the array.|
|**[`Array[@@iterator]()`](/en/webfrontend/Array[@@iterator])**| Returns a new Array Iterator object that contains the values for each index in the array.|

## Examples

### Creating an array

The following example creates an array, `msgArray`, with a length of `0`,
then assigns values to `msgArray[0]` and `msgArray[99]`, changing the length of the array to `100`.

```JavaScript
var msgArray = [];
msgArray[0] = 'Hello';
msgArray[99] = 'world';

if (msgArray.length === 100) {
  console.log('The length is 100.');
}
```

### Creating a two-dimensional array

The following creates a chess board as a two-dimensional array of strings.
The first move is made by copying the 'p' in `(6,4)` to `(4,4)`. The old position `(6,4)`is made blank.

```JavaScript
var board = [
  ['R','N','B','Q','K','B','N','R'],
  ['P','P','P','P','P','P','P','P'],
  [' ',' ',' ',' ',' ',' ',' ',' '],
  [' ',' ',' ',' ',' ',' ',' ',' '],
  [' ',' ',' ',' ',' ',' ',' ',' '],
  [' ',' ',' ',' ',' ',' ',' ',' '],
  ['p','p','p','p','p','p','p','p'],
  ['r','n','b','q','k','b','n','r'] ];

console.log(board.join('\n') + '\n\n');

// Move King's Pawn forward 2
board[4][4] = board[6][4];
board[6][4] = ' ';
console.log(board.join('\n'));
```

Here is the output:

```JavaScript
R,N,B,Q,K,B,N,R
P,P,P,P,P,P,P,P
 , , , , , , ,
 , , , , , , ,
 , , , , , , ,
 , , , , , , ,
p,p,p,p,p,p,p,p
r,n,b,q,k,b,n,r

R,N,B,Q,K,B,N,R
P,P,P,P,P,P,P,P
 , , , , , , ,
 , , , , , , ,
 , , , ,p, , ,
 , , , , , , ,
p,p,p,p, ,p,p,p
r,n,b,q,k,b,n,r
```

### Using an array to tabulate a set of values

```JavaScript
values = [];
for (var x = 0; x < 10; x++){
 values.push([
  2 ** x,
  2 * x ** 2
 ])
};
console.table(values)
```

Results in

```JavaScript
0 1 0
1 2 2
2 4 8
3 8 18
4 16 32
5 32 50
6 64 72
7 128 98
8 256 128
9 512 162
```

(First column is the (index))

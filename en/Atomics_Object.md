TOPICS: Atomics
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# JavaScript `Atomics` Object

The `Atomics` object provides atomic operations as static methods.
They are used with [`SharedArrayBuffer`](/en/webfrontend/SharedArrayBuffer) objects.

The Atomic operations are installed on an Atomics module.
Unlike the other global objects, Atomics is not a constructor.
You cannot use it with a
[new operator](/en/webfrontend/new_operator) or invoke the Atomics object as a function.
All properties and methods of Atomics are static (as is the case with the
[`Math`](/en/webfrontend/Math) object, for example).

## Properties

| Properties | Despcription |
| :-- | :-- |
|**`Atomics[Symbol.toStringTag]`**|The value of this property is `"Atomics"`.|

## Methods

### Atomic operations

When memory is shared, multiple threads can read and write the same data in memory.
Atomic operations make sure that predictable values are written and read,
that operations are finished before the next operation starts and that operations are not interrupted.

| Methods | Despcription |
| :-- | :-- |
|**[`Atomics.add()`](/en/webfrontend/Atomics.add)**| Adds the provided value to the existing value at the specified index of the array. Returns the old value at that index.|
|**[`Atomics.and()`](/en/webfrontend/Atomics.and)**| Computes a bitwise AND on the value at the specified index of the array with the provided value. Returns the old value at that index.|
|**[`Atomics.compareExchange()`](/en/webfrontend/Atomics.compareExchange)**| Stores a value at the specified index of the array, if it equals a value. Returns the old value.|
|**[`Atomics.exchange()`](/en/webfrontend/Atomics.exchange)**| Stores a value at the specified index of the array. Returns the old value.|
|**[`Atomics.load()`](/en/webfrontend/Atomics.load)**| Returns the value at the specified index of the array.|
|**[`Atomics.or()`](/en/webfrontend/Atomics.or)**| Computes a bitwise OR on the value at the specified index of the array with the provided value. Returns the old value at that index.|
|**[`Atomics.store()`](/en/webfrontend/Atomics.store)**| Stores a value at the specified index of the array. Returns the value.|
|**[`Atomics.sub()`](/en/webfrontend/Atomics.sub)**| Subtracts a value at the specified index of the array. Returns the old value at that index.|
|**[`Atomics.xor()`](/en/webfrontend/Atomics.xor)**| Computes a bitwise XOR on the value at the specified index of the array with the provided value. Returns the old value at that index.|

### Wait and notify

The [`wait()`](/en/webfrontend/Atomics.wait) and [`notify()`](/en/webfrontend/Atomics.notify) methods
are modeled on Linux futexes ("fast user-space mutex") and provide ways for waiting until a certain
condition becomes true and are typically used as blocking constructs.

| Methods | Despcription |
| :-- | :-- |
|**[`Atomics.wait()`](/en/webfrontend/Atomics.wait)**| Verifies that the specified index of the array still contains a value and sleeps awaiting or times out. Returns either `"ok"`, `"not-equal"`, or `"timed-out"`. If waiting is not allowed in the calling agent then it throws an Error exception (most browsers will not allow [`wait()`](/en/webfrontend/Atomics.wait) on the browser's main thread).|
|**[`Atomics.notify()`](/en/webfrontend/Atomics.notify)**| Notifies agents that are waiting on the specified index of the array. Returns the number of agents that were notified.|
|**[`Atomics.isLockFree(size)`](/en/webfrontend/Atomics.isLockFree)**| An optimization primitive that can be used to determine whether to use locks or atomic operations. Returns `true`, if an atomic operation on arrays of the given element size will be implemented using a hardware atomic operation (as opposed to a lock). Experts only.|

## Compatibility notes

Prior to Firefox 48, the latest API names and semantics weren't implemented yet.
The changes between Firefox version 46 and version 48 are:

- The methods `Atomics.futexWakeOrRequeue()` and `Atomics.fence()` are now removed entirely
  (bug 1259544 and bug 1225028).
- The methods `Atomics.wait()` and `Atomics.wake()` were named `Atomics.futexWait()`
  and `Atomics.futexWake()` (bug 1260910). Note: The old names have been removed in version 49
  and later (bug 1262062). Atomics.wake() has then been renamed to `Atomics.notify()` in version 63.
- The properties `Atomics.OK`, `Atomics.TIMEDOUT`, `Atomics.NOTEQUAL` have been removed.
  The `Atomics.wait()` method now returns the strings "ok", "timed-out" and "not-equal" (bug 1260835).
- The count parameter of the `Atomics.wake()` method has been changed: it now defaults to `+Infinity`,
  not `0` (bug 1253350).

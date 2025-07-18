---
title: Atomics
slug: Web/JavaScript/Reference/Global_Objects/Atomics
page-type: javascript-namespace
browser-compat: javascript.builtins.Atomics
sidebar: jsref
---

The **`Atomics`** namespace object contains static methods for carrying out atomic operations. They are used with {{jsxref("SharedArrayBuffer")}} and {{jsxref("ArrayBuffer")}} objects.

## Description

Unlike most global objects, `Atomics` is not a constructor. You cannot use it with the [`new` operator](/en-US/docs/Web/JavaScript/Reference/Operators/new) or invoke the `Atomics` object as a function. All properties and methods of `Atomics` are static (just like the {{jsxref("Math")}} object).

### Atomic operations

When memory is shared, multiple threads can read and write the same data in memory. Atomic operations make sure that predictable values are written and read, that operations are finished before the next operation starts and that operations are not interrupted.

### Wait and notify

The `wait()` and `notify()` methods are modeled on Linux futexes ("fast user-space mutex") and provide ways for waiting until a certain condition becomes true and are typically used as blocking constructs.

## Static properties

- `Atomics[Symbol.toStringTag]`
  - : The initial value of the [`[Symbol.toStringTag]`](/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/toStringTag) property is the string `"Atomics"`. This property is used in {{jsxref("Object.prototype.toString()")}}.

## Static methods

- {{jsxref("Atomics.add()")}}
  - : Adds the provided value to the existing value at the specified index of the array. Returns the old value at that index.
- {{jsxref("Atomics.and()")}}
  - : Computes a bitwise AND on the value at the specified index of the array with the provided value. Returns the old value at that index.
- {{jsxref("Atomics.compareExchange()")}}
  - : Stores a value at the specified index of the array, if it equals a value. Returns the old value.
- {{jsxref("Atomics.exchange()")}}
  - : Stores a value at the specified index of the array. Returns the old value.
- {{jsxref("Atomics.isLockFree()")}}
  - : An optimization primitive that can be used to determine whether to use locks or atomic operations. Returns `true` if an atomic operation on arrays of the given element size will be implemented using a hardware atomic operation (as opposed to a lock). Experts only.
- {{jsxref("Atomics.load()")}}
  - : Returns the value at the specified index of the array.
- {{jsxref("Atomics.notify()")}}
  - : Notifies agents that are waiting on the specified index of the array. Returns the number of agents that were notified.
- {{jsxref("Atomics.or()")}}
  - : Computes a bitwise OR on the value at the specified index of the array with the provided value. Returns the old value at that index.
- {{jsxref("Atomics.pause()")}}
  - : Provides a micro-wait primitive that hints to the CPU that the caller is spinning while waiting on access to a shared resource. This allows the system to reduce the resources allocated to the core (such as power) or thread, without yielding the current thread.
- {{jsxref("Atomics.store()")}}
  - : Stores a value at the specified index of the array. Returns the value.
- {{jsxref("Atomics.sub()")}}
  - : Subtracts a value at the specified index of the array. Returns the old value at that index.
- {{jsxref("Atomics.wait()")}}
  - : Verifies that the specified index of the array still contains a value and sleeps awaiting or times out. Returns either `"ok"`, `"not-equal"`, or `"timed-out"`. If waiting is not allowed in the calling agent then it throws an exception. (Most browsers will not allow `wait()` on the browser's main thread.)
- {{jsxref("Atomics.waitAsync()")}}
  - : Waits asynchronously (i.e., without blocking, unlike `Atomics.wait`) on a shared memory location and returns an object representing the result of the operation.
- {{jsxref("Atomics.xor()")}}
  - : Computes a bitwise XOR on the value at the specified index of the array with the provided value. Returns the old value at that index.

## Examples

### Using Atomics

```js
const sab = new SharedArrayBuffer(1024);
const ta = new Uint8Array(sab);

ta[0]; // 0
ta[0] = 5; // 5

Atomics.add(ta, 0, 12); // 5
Atomics.load(ta, 0); // 17

Atomics.and(ta, 0, 1); // 17
Atomics.load(ta, 0); // 1

Atomics.compareExchange(ta, 0, 5, 12); // 1
Atomics.load(ta, 0); // 1

Atomics.exchange(ta, 0, 12); // 1
Atomics.load(ta, 0); // 12

Atomics.isLockFree(1); // true
Atomics.isLockFree(2); // true
Atomics.isLockFree(3); // false
Atomics.isLockFree(4); // true

Atomics.or(ta, 0, 1); // 12
Atomics.load(ta, 0); // 13

Atomics.store(ta, 0, 12); // 12

Atomics.sub(ta, 0, 2); // 12
Atomics.load(ta, 0); // 10

Atomics.xor(ta, 0, 1); // 10
Atomics.load(ta, 0); // 11
```

### Waiting and notifying

Given a shared `Int32Array`:

```js
const sab = new SharedArrayBuffer(1024);
const int32 = new Int32Array(sab);
```

A reading thread is sleeping and waiting on location 0 because the provided value matches what is stored at the provided index.
The reading thread will not move on until the writing thread has called `Atomics.notify()` on position 0 of the provided typed array.
Note that if, after being woken up, the value of location 0 has not been changed by the writing thread, the reading thread will **not** go back to sleep, but will continue on.

```js
Atomics.wait(int32, 0, 0);
console.log(int32[0]); // 123
```

A writing thread stores a new value and notifies the waiting thread once it has written:

```js
console.log(int32[0]); // 0;
Atomics.store(int32, 0, 123);
Atomics.notify(int32, 0, 1);
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{jsxref("ArrayBuffer")}}
- [JavaScript typed arrays](/en-US/docs/Web/JavaScript/Guide/Typed_arrays) guide
- [Web Workers](/en-US/docs/Web/API/Web_Workers_API)
- [Shared Memory – a brief tutorial](https://github.com/tc39/proposal-ecmascript-sharedmem/blob/main/TUTORIAL.md) in the TC39 ecmascript-sharedmem proposal
- [A Taste of JavaScript's New Parallel Primitives](https://hacks.mozilla.org/2016/05/a-taste-of-javascripts-new-parallel-primitives/) on hacks.mozilla.org (2016)

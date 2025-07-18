---
title: SharedArrayBuffer[Symbol.species]
short-title: "[Symbol.species]"
slug: Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer/Symbol.species
page-type: javascript-static-accessor-property
browser-compat: javascript.builtins.SharedArrayBuffer.@@species
sidebar: jsref
---

The **`SharedArrayBuffer[Symbol.species]`** static accessor property returns the constructor used to construct return values from `SharedArrayBuffer` methods.

> [!WARNING]
> The existence of `[Symbol.species]` allows execution of arbitrary code and may create security vulnerabilities. It also makes certain optimizations much harder. Engine implementers are [investigating whether to remove this feature](https://github.com/tc39/proposal-rm-builtin-subclassing). Avoid relying on it if possible.

## Syntax

```js-nolint
SharedArrayBuffer[Symbol.species]
```

### Return value

The value of the constructor (`this`) on which `get [Symbol.species]` was called. The return value is used to construct return values from array buffer methods that create new array buffer.

## Description

The `[Symbol.species]` accessor property returns the default constructor for `SharedArrayBuffer` objects. Subclass constructors may override it to change the constructor assignment. The default implementation is basically:

```js
// Hypothetical underlying implementation for illustration
class SharedArrayBuffer {
  static get [Symbol.species]() {
    return this;
  }
}
```

Because of this polymorphic implementation, `[Symbol.species]` of derived subclasses would also return the constructor itself by default.

```js
class SubArrayBuffer extends SharedArrayBuffer {}
SubArrayBuffer[Symbol.species] === SubArrayBuffer; // true
```

When calling array buffer methods that do not mutate the existing array but return a new array buffer instance (for example, [`slice()`](/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer/slice)), the array's `constructor[Symbol.species]` will be accessed. The returned constructor will be used to construct the return value of the array buffer method.

## Examples

### Species in ordinary objects

The `[Symbol.species]` property returns the default constructor function, which is the `SharedArrayBuffer` constructor for `SharedArrayBuffer`.

```js
SharedArrayBuffer[Symbol.species]; // function SharedArrayBuffer()
```

### Species in derived objects

In an instance of a custom `SharedArrayBuffer` subclass, such as `MySharedArrayBuffer`, the `MySharedArrayBuffer` species is the `MySharedArrayBuffer` constructor. However, you might want to overwrite this, in order to return parent `SharedArrayBuffer` objects in your derived class methods:

```js
class MySharedArrayBuffer extends SharedArrayBuffer {
  // Overwrite MySharedArrayBuffer species to the parent SharedArrayBuffer constructor
  static get [Symbol.species]() {
    return SharedArrayBuffer;
  }
}
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{jsxref("SharedArrayBuffer")}}
- {{jsxref("Symbol.species")}}

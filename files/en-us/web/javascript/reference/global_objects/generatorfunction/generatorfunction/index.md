---
title: GeneratorFunction() constructor
short-title: GeneratorFunction()
slug: Web/JavaScript/Reference/Global_Objects/GeneratorFunction/GeneratorFunction
page-type: javascript-constructor
browser-compat: javascript.builtins.GeneratorFunction.GeneratorFunction
sidebar: jsref
---

The **`GeneratorFunction()`** constructor creates {{jsxref("GeneratorFunction")}} objects.

Note that `GeneratorFunction` is _not_ a global object. It can be obtained with the following code:

```js
const GeneratorFunction = function* () {}.constructor;
```

The `GeneratorFunction()` constructor is not intended to be used directly, and all caveats mentioned in the {{jsxref("Function/Function", "Function()")}} description apply to `GeneratorFunction()`.

## Syntax

```js-nolint
new GeneratorFunction(functionBody)
new GeneratorFunction(arg1, functionBody)
new GeneratorFunction(arg1, arg2, functionBody)
new GeneratorFunction(arg1, arg2, /* …, */ argN, functionBody)

GeneratorFunction(functionBody)
GeneratorFunction(arg1, functionBody)
GeneratorFunction(arg1, arg2, functionBody)
GeneratorFunction(arg1, arg2, /* …, */ argN, functionBody)
```

> [!NOTE]
> `GeneratorFunction()` can be called with or without [`new`](/en-US/docs/Web/JavaScript/Reference/Operators/new). Both create a new `GeneratorFunction` instance.

### Parameters

See {{jsxref("Function/Function", "Function()")}}.

## Examples

### Creating and using a GeneratorFunction() constructor

```js
const GeneratorFunction = function* () {}.constructor;
const g = new GeneratorFunction("a", "yield a * 2");
const iterator = g(10);
console.log(iterator.next().value); // 20
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [`function*`](/en-US/docs/Web/JavaScript/Reference/Statements/function*)
- [`function*` expression](/en-US/docs/Web/JavaScript/Reference/Operators/function*)
- [`Function()` constructor](/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/Function)
- [Iterators and generators](/en-US/docs/Web/JavaScript/Guide/Iterators_and_generators) guide
- {{jsxref("Functions", "Functions", "", 1)}}

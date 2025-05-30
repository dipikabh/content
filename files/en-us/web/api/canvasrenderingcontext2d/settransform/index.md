---
title: "CanvasRenderingContext2D: setTransform() method"
short-title: setTransform()
slug: Web/API/CanvasRenderingContext2D/setTransform
page-type: web-api-instance-method
browser-compat: api.CanvasRenderingContext2D.setTransform
---

{{APIRef}}

The **`CanvasRenderingContext2D.setTransform()`** method of the Canvas 2D API resets (overrides) the current transformation to the identity matrix, and then invokes a transformation described by the arguments of this method. This lets you scale, rotate, translate (move), and skew the context.

> [!NOTE]
> See also the {{domxref("CanvasRenderingContext2D.transform()", "transform()")}} method; instead of overriding the current transform matrix, it
> multiplies it with a given one.

## Syntax

```js-nolint
setTransform(a, b, c, d, e, f)
setTransform(matrix)
```

The transformation matrix is described by: <math><semantics><mrow><mo>[</mo><mtable columnalign="center center center" rowspacing="0.5ex"><mtr><mtd><mi>a</mi></mtd><mtd><mi>c</mi></mtd><mtd><mi>e</mi></mtd></mtr><mtr><mtd><mi>b</mi></mtd><mtd><mi>d</mi></mtd><mtd><mi>f</mi></mtd></mtr><mtr><mtd><mn>0</mn></mtd><mtd><mn>0</mn></mtd><mtd><mn>1</mn></mtd></mtr></mtable><mo>]</mo></mrow><annotation encoding="TeX">\left[ \begin{array}{ccc} a & c & e \\ b & d & f \\ 0 & 0 & 1 \end{array} \right]</annotation></semantics></math>.

This transformation matrix gets multiplied on the left of a column vector representing each point being drawn on the canvas, to produce the final coordinate used on the canvas.

### Parameters

`setTransform()` accepts two types of parameters. The older type consists of several parameters representing the individual components of the transformation matrix to set:

- `a` (`m11`)
  - : The cell in the first row and first column of the matrix.
- `b` (`m12`)
  - : The cell in the second row and first column of the matrix.
- `c` (`m21`)
  - : The cell in the first row and second column of the matrix.
- `d` (`m22`)
  - : The cell in the second row and second column of the matrix.
- `e` (`m41`)
  - : The cell in the first row and third column of the matrix.
- `f` (`m42`)
  - : The cell in the second row and third column of the matrix.

Alternatively, you can pass a single parameter which is an object containing the values above as properties. The parameter names are the property keys, and if two synonymous names are both present (e.g., `m11` and `a`), they must be the same number value, or a {{jsxref("TypeError")}} will be thrown. Using the object form allows omitting some parameters — `a` and `d` default to `1`, while the rest default to `0`.

If a point originally had coordinates <math><semantics><mrow><mo>(</mo><mi>x</mi><mo>,</mo><mi>y</mi><mo>)</mo></mrow><annotation encoding="TeX">(x, y)</annotation></semantics></math>, then after the transformation it will have coordinates <math><semantics><mrow><mo>(</mo><mi>a</mi><mi>x</mi><mo>+</mo><mi>c</mi><mi>y</mi><mo>+</mo><mi>e</mi><mo>,</mo><mi>b</mi><mi>x</mi><mo>+</mo><mi>d</mi><mi>y</mi><mo>+</mo><mi>f</mi><mo>)</mo></mrow><annotation encoding="TeX">(ax + cy + e, bx + dy + f)</annotation></semantics></math>. This means:

- `e` and `f` control the horizontal and vertical translation of the context.
- When `b` and `c` are `0`, `a` and `d` control the horizontal and vertical scaling of the context.
- When `a` and `d` are `1`, `b` and `c` control the horizontal and vertical skewing of the context.

### Return value

None ({{jsxref("undefined")}}).

## Examples

### Skewing a shape

This example skews a rectangle both vertically (`.2`) and horizontally (`.8`). Scaling and translation remain unchanged.

#### HTML

```html
<canvas id="canvas"></canvas>
```

#### JavaScript

```js
const canvas = document.getElementById("canvas");
const ctx = canvas.getContext("2d");

ctx.setTransform(1, 0.2, 0.8, 1, 0, 0);
ctx.fillRect(0, 0, 100, 100);
```

#### Result

{{ EmbedLiveSample('Skewing_a_shape', 700, 180) }}

### Retrieving and passing a DOMMatrix object

In the following example, we have two {{htmlelement("canvas")}} elements. We apply a transform to the first one's context using the first type of `setTransform()` and draw a square on it, then retrieve the matrix from it using {{domxref("CanvasRenderingContext2D.getTransform()")}}.

We then apply the retrieved matrix directly to the second canvas context by passing the `DOMMatrix` object directly to `setTransform()` (i.e., the second type), and draw a circle on it.

#### HTML

```html
<!-- First canvas (ctx1) -->
<canvas width="240"></canvas>
<!-- Second canvas (ctx2) -->
<canvas width="240"></canvas>
```

#### CSS

```css
canvas {
  border: 1px solid black;
}
```

#### JavaScript

```js
const canvases = document.querySelectorAll("canvas");
const ctx1 = canvases[0].getContext("2d");
const ctx2 = canvases[1].getContext("2d");

ctx1.setTransform(1, 0.2, 0.8, 1, 0, 0);
ctx1.fillRect(25, 25, 50, 50);

let storedTransform = ctx1.getTransform();
console.log(storedTransform);

ctx2.setTransform(storedTransform);
ctx2.beginPath();
ctx2.arc(50, 50, 50, 0, 2 * Math.PI);
ctx2.fill();
```

#### Result

{{ EmbedLiveSample('Retrieving_and_passing_a_DOMMatrix_object', "100%", 180) }}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- The interface defining this method: {{domxref("CanvasRenderingContext2D")}}
- {{domxref("CanvasRenderingContext2D.transform()")}}

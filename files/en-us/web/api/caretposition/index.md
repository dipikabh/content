---
title: CaretPosition
slug: Web/API/CaretPosition
page-type: web-api-interface
browser-compat: api.CaretPosition
---

{{ APIRef("CSSOM") }}

The `CaretPosition` interface represents the caret position, an indicator for the text insertion point. You can get a `CaretPosition` using the {{domxref("Document.caretPositionFromPoint()")}} method.

## Instance properties

_This interface doesn't inherit any properties._

- {{domxref("CaretPosition.offsetNode")}} {{ReadOnlyInline}}
  - : Returns a {{domxref("Node")}} containing the found node at the caret's position.
- {{domxref("CaretPosition.offset")}} {{ReadOnlyInline}}
  - : Returns a `long` representing the character offset in the caret position node.

## Instance methods

- {{domxref("CaretPosition.getClientRect")}}
  - : Returns the client rectangle for the caret range.

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{domxref("Document.caretPositionFromPoint()")}}
- {{domxref("Range")}}
- {{domxref("Node")}}

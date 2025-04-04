---
title: "SVGFECompositeElement: height property"
short-title: height
slug: Web/API/SVGFECompositeElement/height
page-type: web-api-instance-property
browser-compat: api.SVGFECompositeElement.height
---

{{APIRef("SVG")}}

The **`height`** read-only property of the {{domxref("SVGFECompositeElement")}} interface describes the vertical size of an SVG filter primitive as a {{domxref("SVGAnimatedLength")}}.

It reflects the {{SVGElement("feComposite")}} element's {{SVGAttr("height")}} filter primitive attribute. The `<feComposite>` SVG filter primitive combines two input images using a Porter-Duff compositing operation. The attribute is a [`<length>`](/en-US/docs/Web/SVG/Guides/Content_type#length) or a [`<percentage>`](/en-US/docs/Web/SVG/Guides/Content_type#percentage) relative to the height of the filter region. The default value is `100%`. The property value is a length in user coordinate system units.

## Value

An {{domxref("SVGAnimatedLength")}}.

## Example

```js
const feComposite = document.querySelector("feComposite");
const verticalSize = feComposite.height;
console.log(verticalSize.baseVal.value); // the `height` value
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{domxref("SVGFECompositeElement.width")}}
- CSS {{cssxref("blend-mode")}} data type
- CSS {{cssxref("mix-blend-mode")}} property

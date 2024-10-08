---
title: orientation
slug: Web/Manifest/orientation
page-type: web-manifest-member
browser-compat: html.manifest.orientation
---

{{QuickLinksWithSubpages("/en-US/docs/Web/Manifest")}}

The `orientation` member defines the default orientation for all the website's top-level {{Glossary("Browsing context", "browsing contexts")}}.

> **Note:** `orientation` and/or its specific values might not be supported by a user agent on various display modes because supporting them does not make sense for the particular context.

> [!NOTE]
> The orientation can be changed at runtime via the [Screen Orientation API](/en-US/docs/Web/API/Screen_Orientation_API).

### Values

`orientation` can take one of the following values:

- `any`
- `natural`
- `landscape`
- `landscape-primary`
- `landscape-secondary`
- `portrait`
- `portrait-primary`
- `portrait-secondary`

## Examples

```json
"orientation": "portrait-primary"
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

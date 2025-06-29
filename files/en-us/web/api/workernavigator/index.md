---
title: WorkerNavigator
slug: Web/API/WorkerNavigator
page-type: web-api-interface
browser-compat: api.WorkerNavigator
---

{{APIRef("Web Workers API")}}{{AvailableInWorkers("worker")}}

The **`WorkerNavigator`** interface represents a subset of the {{DOMxRef("Navigator")}} interface allowed to be accessed from a {{DOMxRef("Worker")}}. Such an object is initialized for each worker and is available via the {{DOMxRef("WorkerGlobalScope.navigator", "self.navigator")}} property.

## Instance properties

_The `WorkerNavigator` interface doesn't inherit any property._

- {{DOMxRef("WorkerNavigator.appCodeName")}} {{Deprecated_Inline}} {{ReadOnlyInline}}
  - : Always returns `'Mozilla'`, in any browser. This property is kept only for compatibility purposes.
- {{DOMxRef("WorkerNavigator.appName")}} {{Deprecated_Inline}} {{ReadOnlyInline}}
  - : Returns the official name of the browser. Do not rely on this property to return the correct value.
- {{DOMxRef("WorkerNavigator.appVersion")}} {{Deprecated_Inline}} {{ReadOnlyInline}}
  - : Returns the version of the browser as a string. Do not rely on this property to return the correct value.
- {{DOMxRef("WorkerNavigator.connection")}} {{ReadOnlyInline}}
  - : Provides a {{DOMxRef("NetworkInformation")}} object containing information about the network connection of a device.
- {{domxref("WorkerNavigator.deviceMemory")}} {{ReadOnlyInline}} {{SecureContext_Inline}}
  - : Returns the amount of device memory in gigabytes. This value is an approximation given by rounding to the nearest power of 2 and dividing that number by 1024.
- {{domxref("WorkerNavigator.globalPrivacyControl")}} {{ReadOnlyInline}} {{Experimental_Inline}}
  - : Returns a boolean indicating a user's consent to their information being shared or sold.
- {{domxref("WorkerNavigator.gpu")}} {{ReadOnlyInline}} {{SecureContext_Inline}}
  - : Returns the {{domxref("GPU")}} object for the current worker context. The entry point for the {{domxref("WebGPU_API", "WebGPU API", "", "nocode")}}.
- {{DOMxRef("WorkerNavigator.hardwareConcurrency")}} {{ReadOnlyInline}}
  - : Returns the number of logical processor cores available.
- {{domxref("WorkerNavigator.hid")}} {{ReadOnlyInline}} {{Experimental_Inline}} {{SecureContext_Inline}}
  - : Returns an {{domxref("HID")}} object providing methods for connecting to HID devices already granted permission by the user and listing attached HID devices, and event handlers for responding to HID devices connecting and disconnecting.
- {{DOMxRef("WorkerNavigator.language")}} {{ReadOnlyInline}}
  - : Returns a string representing the preferred language of the user, usually the language of the browser UI. The `null` value is returned when this is unknown.
- {{DOMxRef("WorkerNavigator.languages")}} {{ReadOnlyInline}}
  - : Returns an array of strings representing the languages known to the user, by order of preference.
- {{DOMxRef("WorkerNavigator.locks")}} {{ReadOnlyInline}} {{SecureContext_Inline}}
  - : Returns a {{DOMxRef("LockManager")}} object which provides methods for requesting a new {{DOMxRef('Lock')}} object and querying for an existing {{DOMxRef('Lock')}} object.
- {{DOMxRef("WorkerNavigator.mediaCapabilities")}} {{ReadOnlyInline}}
  - : Returns a {{domxref("MediaCapabilities")}} object that can expose information about the decoding and encoding capabilities for a given format and output capabilities.
- {{DOMxRef("WorkerNavigator.onLine")}} {{ReadOnlyInline}}
  - : Returns a boolean value indicating whether the browser is online.
- {{DOMxRef("WorkerNavigator.permissions")}} {{ReadOnlyInline}}
  - : Returns a {{DOMxRef("Permissions")}} object that can be used to query and update permission status of APIs covered by the [Permissions API](/en-US/docs/Web/API/Permissions_API).
- {{DOMxRef("WorkerNavigator.platform")}} {{Deprecated_Inline}} {{ReadOnlyInline}}
  - : Returns a string representing the platform of the browser. Do not rely on this property to return the correct value.
- {{DOMxRef("WorkerNavigator.product")}} {{Deprecated_Inline}} {{ReadOnlyInline}}
  - : Always returns `'Gecko'`, on any browser. This property is kept only for compatibility purposes.
- {{domxref("WorkerNavigator.serial")}} {{ReadOnlyInline}} {{Experimental_Inline}} {{SecureContext_Inline}}
  - : Returns a {{domxref("Serial")}} object, which represents the entry point into the [Web Serial API](/en-US/docs/Web/API/Web_Serial_API), to enable the control of serial ports.
- {{domxref("WorkerNavigator.serviceWorker")}} {{ReadOnlyInline}} {{SecureContext_Inline}}
  - : Returns a {{domxref("ServiceWorkerContainer")}} object, which provides access to registration, removal, upgrade, and communication with the {{domxref("ServiceWorker")}} objects for the [associated document](https://html.spec.whatwg.org/multipage/browsers.html#concept-document-window).
- {{DOMxRef("WorkerNavigator.storage")}} {{ReadOnlyInline}} {{SecureContext_Inline}}
  - : Returns a {{DOMxRef('StorageManager')}} interface for managing persistence permissions and estimating available storage.
- {{domxref("WorkerNavigator.usb")}} {{ReadOnlyInline}} {{SecureContext_Inline}}
  - : Returns a {{domxref("USB")}} object for the current document, providing access to [WebUSB API](/en-US/docs/Web/API/WebUSB_API) functionality.
- {{DOMxRef("WorkerNavigator.userAgent")}} {{ReadOnlyInline}}
  - : Returns the user agent string for the current browser.
- {{domxref("WorkerNavigator.userAgentData")}} {{ReadOnlyInline}} {{Experimental_Inline}} {{SecureContext_Inline}}
  - : Returns a {{domxref("NavigatorUAData")}} object, which gives access to information about the browser and operating system of the user.

## Instance methods

_The `WorkerNavigator` interface doesn't inherit any method._

- {{domxref("WorkerNavigator.clearAppBadge()")}} {{SecureContext_Inline}}
  - : Clears a badge on the current app's icon and returns a {{jsxref("Promise")}} that resolves with {{jsxref("undefined")}}.
- {{domxref("WorkerNavigator.setAppBadge()")}} {{SecureContext_Inline}}
  - : Sets a badge on the icon associated with this app and returns a {{jsxref("Promise")}} that resolves with {{jsxref("undefined")}}.

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- Other Worker-related interfaces: {{DOMxRef("Worker")}}, {{DOMxRef("WorkerLocation")}}, and {{DOMxRef("WorkerGlobalScope")}}
- [Using web workers](/en-US/docs/Web/API/Web_Workers_API/Using_web_workers)

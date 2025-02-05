---
title: Device Communication
nav_order: 3
---

# Communication Between Devices (Core API)

Protobject Framework enables seamless communication between multiple devices, allowing them to interact dynamically within a distributed system by using Core API. This is achieved through message sending and receiving mechanisms.
{: .fs-6 .fw-300 }

---

## Sending Messages

To send a message from one page to another, use the `Protobject.Core.send(value).to(targetPage);` function. This allows you to transmit data between devices.

### Example:

```javascript
Protobject.Core.send(true).to("main.html");
```

In this example, `true` is sent to `main.html`. The receiving page must be set up to process incoming messages.

## Receiving Messages

To listen for incoming messages, use the `Protobject.Core.onReceived(callback)` function. The callback function is triggered whenever a message is received.

### Example:

```javascript
Protobject.Core.onReceived(function (message) {
  if (message) {
    console.log("Received: ON");
  } else {
    console.log("Received: OFF");
  }
});
```

In this example, the page logs whether it received an `ON` or `OFF` signal.

## Distributed Multi-Device Interaction

Protobject applications consist of:
- **One main page** (e.g., `main.html`).
- **Multiple secondary pages** (e.g., `device1.html`, `device2.html`).

Each page, whether main or secondary, can communicate with the others through message passing.

---
title: Configuration
nav_order: 2
---

# Configuration File (`config.js`)

The `config.js` file is essential for defining the structure of distributed interactive application built with Protobject Framework. This file specifies the connected devices (or application pages), their roles, and debugging preferences.

## Defining Connected Devices

Each page in a Protobject application corresponds to a device or a specific interface within the system. The `Protobject.initialize([])` function takes an array of objects, each representing a device/page with specific attributes.

### Example Configuration

```javascript
Protobject.initialize([
  {
    name: "Main Device",
    page: "index.html",
    main: true,
    remoteDebug: true,
  },
  {
    name: "Secondary Device 1",
    page: "device1.html",
    localDebug: false,
  },
  {
    name: "Secondary Device 2",
    page: "device2.html",
    localDebug: false,
  },
  {
    name: "Secondary Device 3",
    page: "device3.html",
    localDebug: true,
  },
]);
```

## Configuration Parameters

Each object inside `Protobject.initialize([])` can contain the following parameters:

| Parameter   | Type    | Default | Description |
|------------|--------|---------|-------------|
| `name`     | String | Required | Identifier for the device/page. |
| `page`     | String | Required | The corresponding HTML page for this device. |
| `main`     | Boolean | `false` | Marks the main page of the application. Only one page should have `main: true`. |
| `remoteDebug` | Boolean | `false` | If `true`, all connected pages should send error messages, console logs, and warnings to this page. |
| `localDebug` | Boolean | `false` | If `true`, this page does not send logs to the remote debugging page but instead displays logs locally. |

## Understanding Debugging in Multi-Device Applications

Debugging distributed applications can be challenging, especially when different devices are involved. Protobject provides two debugging modes to facilitate this process:

{: .note }
> **In any case, the browser's devtools must be used to view messages and logs for effective troubleshooting.**


### **Local Debugging (`localDebug: true`)**

- Errors, logs, warnings (`console.log`, `console.warn`, etc.) are displayed directly on the same page where they occur.
- Recommended for development, as it allows direct debugging within each device/page.
- If `localDebug` is `true`, this page will NOT send logs to a remote debugging page.

### **Remote Debugging (`remoteDebug: true`)**

- When a page has `remoteDebug: true`, all connected pages without `localDebug: true` will send their logs and errors to this page.
- This allows centralizing logs and debugging information in a single interface.

## Best Practices for Debugging

- **Prefer Local Debugging**: It provides the most direct feedback and does not depend on another device.
- **Use Remote Debugging When Necessary**: If a page is running on a smartphone or embedded device where accessing logs is inconvenient, remote debugging can centralize logs in an easier-to-access page.
- **Avoid Setting `remoteDebug: true` on Multiple Pages**: Only one page should act as the debugging hub; otherwise, logs could become inconsistent.

By understanding and properly configuring the `config.js` file, you can efficiently structure and debug your multi-device interactive applications using the Protobject Framework.


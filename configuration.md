---
title: Configuration
nav_order: 2
---

# Configuration File (`config.js`)

The `config.js` file is essential for defining the structure of distributed interactive application built with Protobject Framework. This file specifies the connected devices (or application pages), their roles, and debugging preferences.

## Enabling Production Mode

Before defining the connected devices and their debugging configuration, you can enable production mode to ensure that your application has a unique identifier, avoiding potential conflicts between multiple instances of the app. This is particularly important when you're deploying your application publicly.

To enable production mode, set `Protobject.setProduction(true)` at the beginning of the `config.js` file:

```javascript
Protobject.setProduction(true);
```

This will generate a unique identifier for the application instance. During development, you can disable production mode by setting `Protobject.setProduction(false)` or simply commenting out the line. This is useful when you're working with a single instance of the application and don't need a unique identifier to prevent collisions.

### Development Mode
- **Enable Production Mode for Public Release**: Always enable production mode when deploying the application publicly to avoid conflicts between instances.
- **Disable During Development**: During development, you can disable production mode as you are likely working with a single instance of the application.

## Defining Connected Devices

Each page in a Protobject application corresponds to a device or a specific interface within the system. The `Protobject.initialize([])` function takes an array of objects, each representing a device/page with specific attributes.

Each object inside `Protobject.initialize([])` can contain the following parameters:

| Parameter   | Type    | Default | Description |
|------------|--------|---------|-------------|
| `name`     | String | Required | Identifier for the device/page. |
| `page`     | String | Required | The corresponding HTML page for this device. |
| `main`     | Boolean | `false` | Marks the main page of the application. Only one page should have `main: true`. |
| `debug`    | string | `local` | Defines how the page handles debug messages. Possible values: `master`, `remote`, `local`  |

## Understanding Debugging in Multi-Device Applications

Debugging distributed applications can be challenging, especially when different devices are involved. Protobject provides two debugging modes to facilitate this process:

{: .note }
> **In any case, the browser's devtools must be used to view messages and logs for effective troubleshooting.**


### **Local Debugging (`debug: "local"`)**

- Errors, logs, warnings (`console.log`, `console.warn`, etc.) are displayed directly on the same page where they occur.
- Recommended for development, as it allows direct debugging within each device/page.

### **Remote Debugging (`debug: "remote"`)**

- When a page has `debug: "remote"`, it will send its logs and errors to the page marked as `master`.
- This allows centralizing logs and debugging information in a single interface.

### **Master Debugging (`debug: "master"`)**

- The page marked as `master` will collect and display all logs sent from pages with `debug: "remote"`.
- It will also display its own logs locally.
- This page serves as the central hub for debugging information from all connected pages.

### Fallback to Main Page as Master

- If no page has `debug: "master"` explicitly set, the page marked as `main: true` will assume the role of the master page by default. This ensures that there is always a central point for collecting and displaying logs, even if no page is designated as `master`.

## Best Practices for Debugging

- **Prefer Local Debugging**: It provides the most direct feedback and does not depend on another device.
- **Use Remote Debugging When Necessary**: If a page is running on a smartphone or embedded device where accessing logs is inconvenient, remote debugging can centralize logs in an easier-to-access page.
- **Avoid Setting `debug: true` on Multiple Pages**: Only one page should act as the debugging hub; otherwise, logs could become inconsistent.

## Example Configuration (`config.js`)

```javascript
Protobject.setProduction(false)
Protobject.initialize([
  {
    name: "Main Device",
    page: "index.html",
    main: true,
    debug: "master", // Collects and displays logs from all connected pages
  },
  {
    name: "Secondary Device 1",
    page: "device1.html",
    debug: "remote", // Sends logs to the master page
  },
  {
    name: "Secondary Device 2",
    page: "device2.html",
    debug: "remote", // Sends logs to the master page
  },
  {
    name: "Secondary Device 3",
    page: "device3.html",
    debug: "local", // Displays logs locally on this page
  },
]);
```

By understanding and properly configuring the `config.js` file, you can efficiently structure and debug your multi-device interactive applications using the Protobject Framework.


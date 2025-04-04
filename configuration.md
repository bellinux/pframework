---
title: Configuration
nav_order: 2
---

# Configuration File (`config.js`)

Properly configuring the `config.js` file ensures a well-structured and debuggable distributed application in the Protobject Framework.
{: .fs-6 .fw-300 }

---

## Example Configuration

```javascript
Protobject.setProduction(false) // Disable production mode during development
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


## Development and Production Mode

During development, you can disable production mode by setting `Protobject.setProduction(false)` at the beginning of the `config.js` file or simply commenting out the line. This is useful when working with a single instance of the application.

For deployment, enable production mode by setting `Protobject.setProduction(true)`. This ensures your application generates a unique identifier (`?ptjuid={random}`) at startup, preventing conflicts between multiple instances of the web app - especially important for public deployment.

## Defining Connected Devices

In a Protobject application, each page represents either a device or a specific interface within the system. The `Protobject.initialize([])` function accepts an array of objects, where each object defines a device or page with specific attributes. These objects can include the following parameters:

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
- **Use Remote Debugging When Necessary**: If a page is running on a smartphone or other device where accessing logs is inconvenient, remote debugging can centralize logs in an easier-to-access page.
- **Avoid Setting `debug: "master"` on Multiple Pages**: Only one page should act as the debugging hub; otherwise, logs could become inconsistent.



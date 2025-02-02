---
title: Protobject Code
nav_order: 1
---

# Protobject Framework Documentation

Welcome to the documentation for **Protobject Framework**, a system designed for building physical, distributed, and interactive applications. With Protobject Framework, you can use HTML5, CSS, and JavaScript to create interactive components across multiple devices, enabling the development of complex distributed systems.

## Getting Started

To use the Protobject Framework in an HTML page, include the following scripts just below the `<body>` tag:

```html
<script src="https://app.protobject.com/framework/p.js"></script>
<script src="config.js"></script>
```

The `config.js` file is used to configure the pages of your interactive application. Below is an example that defines a simple prototype, where a button controls a lamp by turning it on and off.

### Example `config.js`

```javascript
Protobject.initialize([
  {
    name: "Button",
    page: "button.html",
  },
  {
    name: "Lamp",
    page: "index.html",
    main: true // Marks index.html as the main page
  }
]);
```

### Example `index.html` (Lamp Page)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Lamp</title>
  </head>
  <body>
    <script src="https://app.protobject.com/framework/p.js"></script>
    <script src="config.js"></script>
    <script>
      // Create a Lamp component
      const lamp = new Protobject.Lamp({
        width: "100%",
        height: "100%",
        top: "0px",
        left: "0px",
        zIndex: 5
      });

      // Listen for messages and update lamp state
      Protobject.Core.onReceived(function (message) {
        if (message) {
          lamp.setColor({ r: 255, g: 0, b: 0 }); // Turn lamp red when button is pressed
        } else {
          lamp.setColor({ r: 0, g: 0, b: 0 }); // Turn lamp off when button is released
        }
      });
    </script>
  </body>
</html>
```

### Example `button.html` (Button Page)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Button</title>
  </head>
  <body>
    <script src="https://app.protobject.com/framework/p.js"></script>
    <script src="config.js"></script>
    <script>
      // Create a Button component
      const button = new Protobject.Button({
        text: "Click Me",
        style: {
          backgroundColor: "blue",
          color: "white",
          padding: "10px 20px"
        }
      });

      // Send a message when button is pressed
      button.onPressed(() => {
        Protobject.Core.send(true).to("index.html");
      });

      // Send a message when button is released
      button.onRelease(() => {
        Protobject.Core.send(false).to("index.html");
      });
    </script>
  </body>
</html>
```

### How It Works

- The **main page** (`index.html`) displays a lamp.
- The **secondary page** (`button.html`) provides a button interface.
- When the button is pressed, it sends a `true` message to `index.html`, turning the lamp red.
- When the button is released, it sends a `false` message, turning the lamp off.
- A **plus icon (+)** appears on the main page to allow secondary pages to connect (e.g., using a QR code or a link).

## Communication Between Devices

Protobject applications consist of one main page and multiple secondary pages, which may run on different devices such as smartphones, tablets, or PCs.

Devices can communicate by sending and receiving messages using the **Protobject Communication API**.

Example of message transmission:

```javascript
Protobject.Core.send(true).to("index.html");
```

- This sends `true` to `index.html`, triggering the lamp to turn on.
- The `index.html` page listens for incoming messages using `Protobject.Core.onReceived` and updates the lamp accordingly.

This mechanism allows seamless interaction between different components in the system.

## Available Components

In addition to buttons and lamps, the Protobject Framework offers a variety of interactive components. You can find all available components listed in the right sidebar of the documentation.

For more details on each component, refer to the [Protobject Component Reference].

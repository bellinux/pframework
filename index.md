---
title: Home
nav_order: 1
---

# Protobject Framework Documentation

Welcome to the documentation for **Protobject Framework**, a system designed for building physical, distributed, and interactive applications. With Protobject Framework, you can use HTML5, CSS, and JavaScript to create interactive components across multiple devices, enabling the development of complex distributed systems.
{: .fs-6 .fw-300 }

[Getting Started](#getting-started){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[Demo Projects](demo.md){: .btn .fs-5 .mb-4 .mb-md-0 }


---

## Getting Started

To use the Protobject Framework in an HTML page, include the following scripts just below the `<body>` tag:

```html
<script src="https://app.protobject.com/framework/p.js"></script>
<script src="config.js"></script>
```

The `config.js` file is used to configure the pages of your interactive application. Below is an example that defines a simple prototype, where a button controls a lamp by turning it on and off.

### Example `config.js`

```javascript
Protobject.setProduction(true)
Protobject.initialize(
	[
		{ 
			name: "Button",
			page: "button.html",
			debug: "local",
		},
		{ 
			name: "Lamp",
			page: "index.html",
			main: true,
			debug: "master",
		}
	]);
```

### Example `index.html` (Lamp Page)

```html
<!-- This is a simple lamp that turns on with a button. See the file button.html -->

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
    
    <h1 style="font-family:sans-serif; text-align:center; margin-top:20px">This is the lamp</h1>
    <script>
      // This file, index.html, defines a lamp.
      // An instance of the lamp is created with the specified dimensions and position.
      const lamp = new Protobject.Lamp({
        width: "calc(100% - 160px)", // Lamp width
        height: "calc(100% - 160px)", // Lamp height
        top: "80px", // Position from the top
        left: "80px", // Position from the left
        zIndex: 5,
        borderRadius: "20px"
      });

      // Event triggered when a message is received.
      // If the received message is 'true', the lamp turns on with red light.
      // If the message is 'false', the lamp turns off.
      Protobject.Core.onReceived(function (message) {
        if (message) {
          lamp.setColor({ r: 0, g: 255, b: 0 }); // Green light (RGB: 0, 255, 0)
        } else {
          lamp.setColor({ r: 0, g: 0, b: 0 }); // Off (RGB: 0, 0, 0)
        }
      });
    </script>
  </body>
</html>
```

### Example `button.html` (Button Page)

```html
<!-- This page defines the button -->
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
    <h1 style="font-family:sans-serif; text-align:center; margin-top:20px">This is the button</h1>
    <script>
      // A button is created with the following configurations:
      const button = new Protobject.Button({
        text: "Click Me", // Text displayed on the button
        style: {
          backgroundColor: "blue", // Button background color
          color: "white", // Text color
          padding: "10px 20px", // Internal spacing of the button (top-bottom, left-right)
          width: "calc(100% - 160px)", // Lamp width
          height: "calc(100% - 160px)", // Lamp height
          top: "80px", // Position from the top
          left: "80px", // Position from the left
          borderRadius: "20px",
        },
      });

      // An action is defined for when the button is pressed.
      // It displays a message in the console and sends the value 'true' to the "index.html" file.
      button.onPressed(() => {
        Protobject.Core.send(true).to("index.html"); // Send message to the file
      });

      // An action is defined for when the button is released.
      // It displays a message in the console and sends the value 'false' to the "index.html" file.
      button.onRelease(() => {
        Protobject.Core.send(false).to("index.html"); // Send message to the file
      });
    </script>
  </body>
</html>

```

[Edit on Glitch](https://glitch.com/edit/#!/protobject-basic-framework){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 target="_blank"}
[Watch the Video](https://github.com/user-attachments/assets/1f7bdf5d-e470-4a5d-a778-e3f7843a685c){: .btn .fs-5 .mb-4 .mb-md-0 target="_blank"}


{: .note }
> [Glitch](https://glitch.com) is an **excellent platform** for developing with the Protobject Framework.  
> It allows **quick prototyping**, **easy collaboration**, and **real-time updates**.  





### How It Works

- A **[plus icon](https://github.com/user-attachments/assets/c38902b1-f117-4555-be00-2d7c27f699d3){:target="_blank"} (+)** appears on the lamp page to allow the button page to connect (e.g., using a QR code or a link).
- The **main page** (`index.html`) displays a lamp.
- The **secondary page** (`button.html`) provides a button interface.
- When the button is pressed, it sends a `true` message to `index.html`, turning the lamp red.
- When the button is released, it sends a `false` message, turning the lamp off.


### Communication Between Devices

Protobject applications consist of one main page and multiple secondary pages, which may run on different devices such as smartphones, tablets, or PCs.

Devices can communicate by sending and receiving messages using the **[Protobject Core API](communication.md)**.

Example of message transmission:

```javascript
Protobject.Core.send(true).to("index.html");
```

- This sends `true` to `index.html`, triggering the lamp to turn on.
- The `index.html` page listens for incoming messages using `Protobject.Core.onReceived` and updates the lamp accordingly.

This mechanism allows seamless interaction between different components in the system.

### Available Components

In addition to buttons and lamps, the Protobject Framework offers a variety of [interactive components](components.html).

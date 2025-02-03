---
title: Acceleration
parent: Components
nav_order: 3
---

# The Acceleration Component

The `Acceleration` component provides a simple interface for accessing and handling accelerometer data from a device's sensors. It allows setting a callback function to handle accelerometer data.

## Starting the Acceleration component
To start receiving accelerometer data, call the `start` method, with optional frequency in ms. 

```javascript
Protobject.Acceleration.start(300); //generate events each 300 ms
```

## Handling Acceleration Data
To handle the accelerometer data, set a callback function using the `onData` method. This callback function will be called with the acceleration data whenever it changes.

```javascript

Protobject.Acceleration.onData((data) => {
    console.log("X: " + data.x + "; Y: " + data.y + "; Z: " + data.z);
});

```


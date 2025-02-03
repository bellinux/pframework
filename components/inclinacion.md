---
title: Inclination
parent: Components
nav_order: 4
---

# The Inclination Component

The Inclination component provides a simple interface for accessing and handling inclination data from a device's sensors. It allows setting a callback function to handle inclination data.


## Starting the Inclination component
To start receiving inclination data, call the `start` method, with optional frequency in ms. 

```javascript
Protobject.Inclination.start(300); //generate events each 300 ms
```

## Handling Inclination Data
To handle the inclination data, set a callback function using the `onData` method. This callback function will be called with the inclination data whenever it changes.

```javascript

Protobject.Inclination.onData((data) => {
    console.log("X: " + data.x + "; Y: " + data.y + "; Z: " + data.z);
});

```






```


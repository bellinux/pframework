---
title: Orientation 
parent: Components
nav_order: 10
---

# The Orientation  Component

The `Orientation` component provides a simple interface for accessing and handling orientation data from a device's sensors. It allows setting a callback function to handle orientation data.


## Starting the Orientation component
To start receiving orientation data, call the start method, with optional frequency in ms. 


```javascript
Protobject.Orientation.start(300); //generate events each 300 ms
```

## Handling Orientation Data
To handle the orientation data, set a callback function using the `onData` method. This callback function will be called with the orientation data whenever it changes.

```javascript

Protobject.Orientation.onData((data) => {
    console.log("Horizontal: " + data.horizontal + "; Vertical: " + data.vertical + " HorizontalContinuous: " + data.horizontalContinuous + "; VerticalContinuous: " + data.verticalContinuous);
});

```
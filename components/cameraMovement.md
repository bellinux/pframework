---
title: CameraMovement
parent: Components
nav_order: 5
---

# The CameraMovement Component

The `CameraMovement` component facilitates camera-based motion detection. It captures webcam input, and calculates motion direction and magnitude. Users can set a callback function to receive motion data updates.


## Starting CameraMovement Detection
To start detecting camera movements and calculating optical flow, call the `start` method. You can specify an optional frequency (in milliseconds) and an optional camera ID.

```javascript
Protobject.CameraMovement.start(300); //generate events each 300 ms; 0 is the webcam id
```

## Handling Motion Data
To handle motion data, set a callback function using the `onData` method. This callback function will be called with the motion data whenever it changes.

```javascript
Protobject.CameraMovement.onData((data) => {
    console.log("Direction: " +data.direction + "; Magnitude: "+ data.magnitude);
});
```



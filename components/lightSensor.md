---
title: LightSensor 
parent: Components
nav_order: 12
---

# The LightSensor Component

The `LightSensor` component provides functionality to monitor brightness levels using a camera. It supports setting exposure levels and provides real-time brightness data through a callback function.


## Starting the LightSensor
To start monitoring brightness, use the start method. You can specify an optional frequency (in milliseconds) and an optional camera ID.

```javascript
Protobject.LightSensor.start(200, 0); // Starts with a refresh frequency of 200 ms using camera ID 0
```


## Setting Exposure
Adjust the exposure of the camera to enhance or reduce brightness detection:

```javascript
Protobject.LightSensor.setExposure(50); // Sets exposure to 50% (if supported)
```

## Handling Brightness Data
To handle the brightness data, set a callback function using the onData method. This callback function will be called with the brightness value whenever it changes:

```javascript
Protobject.LightSensor.onData((brightness) => {
    console.log("brightness: " + brightness);
});
```

## Stopping the LightSensor
To stop monitoring and release camera resources:

```javascript
Protobject.LightSensor.stop();
```


## Showing Video Preview
To enable the display of the video stream, call the showPreview method, specifying the dimensions and position of the canvas.

```javascript
Protobject.LightSensor.showPreview({ top: 50, left: 50, width: 640, height: 480 });


```

## Hiding Video Preview
To hide the video preview, use the hidePreview method.

```javascript
Protobject.LightSensor.hidePreview();


```



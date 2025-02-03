---
title: PresenceSensor 
parent: Components
nav_order: 11
---

# The PresenceSensor Component

The `PresenceSensor` component provides functionalities to monitor presence using webcam video.


## Setting Baseline and Starting Monitoring

Initialize the `PresenceSensor` component and set the baseline for presence monitoring. You can specify an optional frequency (in milliseconds) and an optional camera ID.

```javascript
Protobject.PresenceSensor.setBaselineAndStartMonitoring(200, 0); //200 is the frequency of detection; 0 is the webcam id
```

## Setting New Baseline
Set a new baseline for presence monitoring.

```javascript
Protobject.PresenceSensor.setNewBaseline();
```

## Handling Data Callback
Register a callback function to handle data when similarity changes.

```javascript

Protobject.PresenceSensor.onData((similarity) => {
  console.log("Image similarity:" + similarity);
});
```

The similarity value ranges from 0 to 1, where:

- A value close to 1 (similarity > 0.8) indicates that no presence is detected.
- A value far from 1 (similarity < 0.8) suggests that something is in the field of vision of the camera.




## Showing Video Preview
To enable the display of the video stream, call the showPreview method, specifying the dimensions and position of the canvas.

```javascript
Protobject.PresenceSensor.showPreview({ top: 50, left: 50, width: 640, height: 480 });


```

## Hiding Video Preview
To hide the video preview, use the hidePreview method.

```javascript
Protobject.PresenceSensor.hidePreview();


```
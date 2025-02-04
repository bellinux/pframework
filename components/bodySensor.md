---
title: BodySensor 
parent: Components
nav_order: 22
---

# The BodySensor Component

The `BodySensor` component facilitates the detection of human bodies using the webcam. It captures webcam video, identifies body landmarks, and provides updated data on detected bodies (position, features). Users can set callback functions to receive updates on bodies and manage the preview display.


> For the best development experience when working with video streams, it is recommended to design for horizontal (landscape) orientation on mobile devices. Working in vertical (portrait) orientation may result in distortion or stretching of the video display.
{: .highlight }

## Starting Body Detection
To begin detecting bodies, use the start method. You can specify an optional frequency (in milliseconds) and an optional camera ID.

```javascript
Protobject.BodySensor.start(200, 0); // Detects bodies every 200 ms using camera ID 0

```

## Handling Body Data
To handle body data, set a callback function using the onData method. This function will be called with body data whenever there are updates.

```javascript
Protobject.BodySensor.onData((data) => {
    console.log("Body Data: ", data);
});
```


## Showing Body Preview
To enable the display of detected bodies on a canvas, you can add a method to handle the preview. For example:

```javascript
Protobject.BodySensor.showPreview({ top: 50, left: 50, width: 640, height: 480 });

```
The preview shows two yellow rectangles at the positions (0.1, 0.1) to (0.9, 0.9) and (0.2, 0.2) to (0.8, 0.8), which can be used to calibrate the video coordinates to real-world objects.

## Hiding Body Preview
To hide the body preview canvas, you can use a method to do so. For example:

```javascript
Protobject.BodySensor.hidePreview();

```

## Flipping the Preview
To flip the preview display (for mirror-like effect), you can use the flip method:

```javascript
Protobject.BodySensor.flip(true); // set to true to enable flipping

```

More information:

- [Mediapipe Body Landmark](https://ai.google.dev/edge/mediapipe/solutions/vision/pose_landmarker/web_js)
- [Landmark details](https://ai.google.dev/static/mediapipe/images/solutions/pose_landmarks_index.png)

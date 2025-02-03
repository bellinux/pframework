---
title: FaceSensor 
parent: Components
nav_order: 23
---

# The FaceSensor Component

The `FaceSensor` component facilitates the detection of faces using the webcam. It captures webcam video, identifies faces, and provides updated data on detected faces (position, features). Users can set callback functions to receive updates on faces and manage the preview display.

<mark>*Notice: For the best development experience when working with video streams, it is recommended to design for horizontal (landscape) orientation on mobile devices. Working in vertical (portrait) orientation may result in distortion or stretching of the video display.*</mark>


## Starting Face Detection
To begin detecting faces, use the start method. You can specify an optional frequency (in milliseconds) and an optional camera ID.

```javascript
Protobject.FaceSensor.start(200, 0); // Detects faces every 200 ms using camera ID 0

```

## Handling Face Data
To handle face data, set a callback function using the onData method. This function will be called with face data whenever there are updates.

```javascript
Protobject.FaceSensor.onData((data) => {
    console.log("Face Data: ", data); 
});
```


## Showing Face Preview
To enable the display of detected faces on a canvas, you can add a method to handle the preview. For example:

```javascript
Protobject.FaceSensor.showPreview({ top: 50, left: 50, width: 640, height: 480 });

```
The preview shows two yellow rectangles at the positions (0.1, 0.1) to (0.9, 0.9) and (0.2, 0.2) to (0.8, 0.8), which can be used to calibrate the video coordinates to real-world objects.

## Hiding Face Preview
To hide the face preview canvas, you can use a method to do so. For example:

```javascript
Protobject.FaceSensor.hidePreview();

```

## Flipping the Preview
To flip the preview display (for mirror-like effect), you can use the flip method:

```javascript
Protobject.FaceSensor.flip(true); // set to true to enable flipping

```

More information:

- [Mediapipe Face Landmark](https://ai.google.dev/edge/mediapipe/solutions/vision/face_landmarker/web_js)
- [Landmark details](https://storage.googleapis.com/mediapipe-assets/documentation/mediapipe_face_landmark_fullsize.png)

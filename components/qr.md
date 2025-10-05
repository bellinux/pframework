---
title: QR
parent: Components
nav_order: 110
---

# The QR Component

The `QR` component provides an easy way to scan QR codes using the device's camera. It handles camera access, continuously scans the video feed for a QR code, and returns the decoded data through a simple callback function.

## Starting QR Scanning

To activate the camera and begin scanning for QR codes, call the `start` method. You can specify an optional `cameraId` to select which camera to use.

```javascript
// Use the first available camera (often the back camera on mobile).
Protobject.QR.start(0);
```

## Handling QR Data
To process the data from a scanned QR code, set a callback function using the `onData` method. This callback will be executed as soon as a QR code is successfully detected, receiving the decoded data as a string.

```javascript
Protobject.QR.onData((data) => {
    console.log("QR Code Detected:", data);
});
```



## Showing the Camera Preview
To display a live feed from the camera on your webpage, use the `showPreview` method. You can specify the position and dimensions of the preview window.

```javascript
Protobject.QR.showPreview({ top: 50, left: 50, width: '640px', height: '480px' });

```



## Hiding the Camera Preview
If you no longer wish to display the live camera feed, you can hide it by calling the `hidePreview` method. The scanning will continue in the background.

```javascript
Protobject.QR.hidePreview();
```


## Stopping the Scan
To completely stop the camera feed and release all resources, call the `stop` method. This is important for saving battery and ensuring user privacy.

```javascript
Protobject.QR.stop();
```

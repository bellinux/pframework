---
title: ArUco 
parent: Components
nav_order: 20
---

# The ARuco Component

The `ARuco` component facilitates the detection of ArUco markers using the webcam. It captures webcam video, identifies ArUco markers, and provides updated data on detected markers (size, position). Users can set callback functions to receive updates on markers and manage the preview display.

<mark>*Notice: For the best development experience when working with video streams, it is recommended to design for horizontal (landscape) orientation on mobile devices. Working in vertical (portrait) orientation may result in distortion or stretching of the video display.*</mark>


## Starting Marker Detection
To start detecting ArUco markers, call the start method. You can specify an optional frequency (in milliseconds) and an optional camera ID.

```javascript
Protobject.Aruco.start(200, 0); // generates events every 200 ms; 0 is the webcam id

```

## Handling Marker Data
To handle marker data, set a callback function using the onData method. This function will be called with marker data whenever there are updates.

```javascript
Protobject.Aruco.onData((data) => {
    console.log("Marker Data: ", data);
});

```


## Showing Marker Preview
To enable the display of detected markers on the canvas, call the showPreview method, specifying the dimensions and position of the canvas.

```javascript
Protobject.Aruco.showPreview({ top: 50, left: 50, width: 640, height: 480 });


```

## Hiding Marker Preview
To hide the marker preview canvas, use the hidePreview method.

```javascript
Protobject.Aruco.hidePreview();


```

## Data Structure
When receiving marker data, the structure is as follows:

```javascript
{
    "markerId": {
        "position": { "x": number, "y": number },
        "size": number
    },
    ...
}



```

Where:

* markerId is the ID of the detected marker.
* position contains the x and y coordinates of the marker's center.
* size is the area of the marker.

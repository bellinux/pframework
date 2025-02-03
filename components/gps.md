---
title: GPS 
parent: Components
nav_order: 15
---

# The GPS Component

The `GPS` component provides functionality to retrieve and monitor geolocation data from the device's GPS.

## Starting GPS Tracking
To start tracking GPS data:

```javascript
Protobject.GPS.start();
```

## Handling GPS Data Updates
To handle GPS data updates, set a callback function using the onData method. This callback function will be called with the GPS data whenever it changes:

```javascript
Protobject.GPS.onData((data) => {
    console.log(`Latitude: ${data.latitude}`);
    console.log(`Longitude: ${data.longitude}`);
    console.log(`Speed: ${data.speed}`);
    console.log(`Accuracy: ${data.accuracy}`);
    console.log(`Altitude: ${data.altitude}`);
});
```

## Stopping GPS Tracking
To stop GPS tracking:

```javascript
Protobject.GPS.stop();
```


## Example Usage
```javascript

Protobject.GPS.onData((data) => {
    console.log(`Latitude: ${data.latitude}`);
    console.log(`Longitude: ${data.longitude}`);
});

Protobject.GPS.start();

```


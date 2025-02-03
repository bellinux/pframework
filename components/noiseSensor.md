---
title: NoiseSensor
parent: Components
nav_order: 6
---

# The NoiseSensor Component

The `NoiseSensor` component provides functionality for noise detection. It captures audio from the microphone, computes the amplitude of the audio signal, and provides callbacks with noise intensity updates.



## Starting Noise Detection
To start detecting noise levels, call the `start` method, with optional frequency in ms. 

```javascript
Protobject.NoiseSensor.start(300) //generate events each 300 ms
```

## Handling Noise Data
To handle noise data updates, set a callback function using the `onData` method. This callback function will be called with the noise intensity whenever it changes.

```javascript
Protobject.NoiseSensor.onData((intensity) => {
    console.log("Noise intensity: " + intensity);
});
``` 

## Stopping Noise Detection
To stop noise detection and release resources, call the `stop` method.

```javascript
Protobject.NoiseSensor.stop();
```
---
title: AudioClassifier 
parent: Components
nav_order: 24
---

# The AudioClassifier Component

The `AudioClassifier` component facilitates the detection and classification of audio inputs using the microphone. It captures audio, identifies different sound categories, and provides updated data on detected audio events. Users can set callback functions to receive updates on audio classifications.


## Starting Audio Detection
To start classifying audio, call the start method.

```javascript
Protobject.AudioClassifier.start();

```

## Handling Audio Data
To handle audio classification data, set a callback function using the onData method. This function will be called with audio data whenever there are updates.

```javascript
Protobject.AudioClassifier.onData((data) => {
    console.log("Audio Event Data: ", data); 
});

```

More information:

- [Mediapipe Audio Classification](https://ai.google.dev/edge/mediapipe/solutions/audio/audio_classifier/web_js)

---
title: VoiceRecognition 
parent: Components
nav_order: 16
---

# The VoiceRecognition Component

The `VoiceRecognition` component provides an interface for integrating speech recognition capabilities into your application.

## Starting Voice Recognition
To start voice recognition:

```javascript

Protobject.VoiceRecognition.start('en-US');
```

## Handling Recognized Data
Set a callback function using the onData method to handle recognized speech:

```javascript

Protobject.VoiceRecognition.onData((transcript) => {
    console.log(`Recognized Speech: ${transcript}`);
});

```

## Handling Recognition Finish
Set a callback function using the onFinish method to handle the completion of speech recognition:

```javascript

Protobject.VoiceRecognition.onFinish(() => {
    console.log("Speech recognition finished.");
});

```
## Stopping Voice Recognition

To stop voice recognition:

```javascript

Protobject.VoiceRecognition.stop();

```


## Example Usage
```javascript
Protobject.VoiceRecognition.onData((transcript) => {
    console.log(`Recognized Speech: ${transcript}`);
});

Protobject.VoiceRecognition.start('en-US');
```

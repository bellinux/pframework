---
title: TextToSpeech 
parent: Components
nav_order: 14
---

# The TextToSpeech Component

The `LightSensor` component provides a straightforward interface for converting text to speech.

## Playing Text-to-Speech
To convert text to speech and play it:

```javascript

Protobject.TextToSpeech.play("en", "Hello, world!");
```

You can specify the language and the text to be spoken.

## Stopping Speech
To stop the current speech playback:

```javascript
Protobject.TextToSpeech.stop();
```

## Handling Speech Completion
To execute code when speech playback ends:

```javascript

Protobject.TextToSpeech.onTTSEnd(() => {
    console.log("Speech playback ended.");
});
```

## Example Usage

```javascript

Protobject.TextToSpeech.onTTSEnd(() => {
    console.log("Speech playback ended.");
});

Protobject.TextToSpeech.play("en", "Hello, world!");

```




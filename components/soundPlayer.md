---
title: SoundPlayer
parent: Components
nav_order: 7
---

# The SoundPlayer Component

The `SoundPlayer` component provides a convenient interface for playing audio files, specifically supporting .mp3 format URLs. It includes methods for playing, pausing, stopping, adjusting volume, and enabling loop playback.



## Playing Audio
To play an audio file from a URL, use the `play` method. Specify the URL and optionally set loop to true for continuous playback.

```javascript
const player = new Protobject.SoundPlayer();
player.play('https://www.w3schools.com/html/horse.mp3', true);
```

## Pausing and Stopping Audio
Pause and stop currently playing audio using the `pause` and `stop` methods, respectively.

```javascript
player.pause();
player.stop();

```


## Adjusting Volume
Adjust the volume of the audio using the `setVolume` method. The volume value should be between 0 and 100.

```javascript

player.setVolume(50); // Set volume to 50%
```

## Setting Loop Playback
Enable or disable loop playback using the `setLoop` method.

```javascript
player.setLoop(true); // Enable loop playback

```
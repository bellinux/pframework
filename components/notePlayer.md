---
title: NotePlayer 
parent: Components
nav_order: 13
---

# The NotePlayer Component

The `LightSensor` component provides a simple interface for playing musical notes, allowing dynamic loading of instrument samples and triggering notes.

## Creating a NotePlayer Instance
To create a new instance of NotePlayer:

```javascript

const options = {
    A1: "https://tonejs.github.io/audio/casio/A1.mp3",
    // Add more notes as needed
};
const player = new Protobject.NotePlayer(options);
```

const player = new Protobject.NotePlayer(options);

Alternatively, you can pass a single URL string as options:

```javascript
const singleNoteUrl = "https://tonejs.github.io/audio/casio/A1.mp3";
const player = new Protobject.NotePlayer(singleNoteUrl);
```

## Loading the Instrument
The instrument samples are loaded asynchronously.

```javascript

player.onInstrumentLoaded(() => {
    console.log("Instrument loaded successfully.");
});
```

## Playing Notes
To play a note:

```javascript

player.play("A1"); // Play note A1

```

You can also play notes by frequency:
```javascript

player.play(440); // Play middle A

```

## Stopping Playback
To stop the currently playing note:

```javascript
player.stop();
```

## Handling Instrument Loading Completion
To execute code once the instrument has finished loading:

```javascript
player.onInstrumentLoaded(() => {
    console.log("Instrument loaded successfully.");
});
```

## Example Usage
``` javascript


const options = {
    A1: "https://tonejs.github.io/audio/casio/A1.mp3",
    B1: "https://tonejs.github.io/audio/casio/B1.mp3",
    // Add more notes as needed
};

const player = new Protobject.NotePlayer(options);

player.onInstrumentLoaded(() => {
    console.log("Instrument loaded successfully.");
    player.play("A1");
});
```

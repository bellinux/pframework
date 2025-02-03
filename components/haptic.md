---
title: Haptic 
parent: Components
nav_order: 18
---

# The Haptic Component

The `Haptic` component provides methods to handle device vibration.



## Starting Haptic Feedback
To initiate haptic feedback, display a confirmation popup and start vibration upon user confirmation:

```javascript
Protobject.Haptic.start();
```

## Vibrate with Custom Patterns
To vibrate the device with a custom vibration pattern:

```javascript
// Vibrate with a pattern of 200ms on, 100ms off, 200ms on
Protobject.Haptic.vibrate([200, 100, 200]);

```


## Usage Example
```javascript
Protobject.Haptic.start();

const button = new Protobject.Button();
button.onPressed(() => {
  Protobject.Haptic.vibrate([200, 100, 200]);
});
```


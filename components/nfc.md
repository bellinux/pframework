---
title: NFC
parent: Components
nav_order: 120
---

# The NFC Component

The `NFC` component enables interaction with NFC (Near Field Communication) tags. It handles the browser's security prompts and permissions by displaying its own confirmation button, listens for NFC tags, and provides a simple callback to retrieve the unique serial number (ID) of a compatible tag.

## Starting NFC Scanning

To begin scanning for NFC tags, simply call the `start` method. This action will immediately display a popup on the screen, asking the user to confirm the action.

The `start` method returns a Promise, which allows you to know when scanning has officially begun (after the user's confirmation) or if an error occurred (for example, if the user denies the browser's permission prompt).

```javascript
// This single call will show the confirmation popup to the user.
Protobject.NFC.start();
```

You can also handle the promise to respond to success or failure using the `.then()` and `.catch()` methods.

```javascript
Protobject.NFC.start()
    .then(() => {
        // This code runs only after the user confirms and scanning is active.
        console.log("NFC scanning is active. Please tap a tag.");
    })
    .catch(error => {
        // This code runs if the user denies permission or another error occurs.
        console.error("NFC could not be started.", error);
    });
```

## Handling NFC Data

To process data from a scanned NFC tag, set a callback function using the `onData` method. The callback receives one argument:
* On a successful read, it receives the tag's serial number (ID) as a string.
* If an incompatible or unformatted tag is scanned, it receives the string "err: no compatible".



```javascript
Protobject.NFC.onData((id) => {
    if (id === "err: no compatible") {
        console.log("An incompatible NFC tag was detected.");
    } else {
        console.log("NFC Tag ID:", id);
        document.getElementById("result").innerText = id;
    }
});
```


## Stopping the Scan
To disable the NFC reader and stop listening for tags, call the `stop` method. This releases the hardware and is a good practice.


```javascript
Protobject.NFC.stop();
```

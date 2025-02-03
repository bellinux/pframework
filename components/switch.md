---
title: Switch
parent: Components
nav_order: 8
---

# The Switch Component

The `Switch` component provides a customizable switch interface. It allows users to create interactive switches with customizable styles, text labels, and callbacks for state changes.


## Create the Switch
To create a switch, instantiate the `Switch` class with optional configuration parameters. By default, the switch will be initialized in the 'off' state.

```javascript
const switchInstance = new Protobject.Switch({
    onText: 'ON', 
    offText: 'OFF', 
    width: 90, 
    height: 180,
    top: 30,
    left: 30,
    fontSize: 20,
    onTurnedOn: () => console.log('Switch turned ON'),
    onTurnedOff: () => console.log('Switch turned OFF'),
    styleOff: { backgroundColor: 'grey' },
    styleOn: { backgroundColor: 'green' }
});
```

### Customizing Styles
You can customize the styles of the switch container, knob, and text elements using the respective `setStyleContainer`, `setStyleKnob`, and `setStyleTextElement` methods.

```javascript

switchInstance.setStyleContainer({ backgroundColor: 'blue', borderRadius: '15px' });
switchInstance.setStyleKnob({ backgroundColor: 'white', boxShadow: '0 0 5px rgba(0,0,0,0.3)' });
switchInstance.setStyleTextElement({ color: 'black', fontWeight: 'bold' });
```

### Setting Text Labels
Set custom text labels for the 'on' and 'off' states using the `setOnOffText` method.

```javascript

switchInstance.setOnOffText('1', 'O');
```

### Setting Position
Adjust the position of the switch on the screen using the `setPosition` method.

```javascript

switchInstance.setPosition(100, 50);
```

### Handling State Changes
Register callbacks for when the switch is turned on or off using the `onTurnedOn` and `onTurnedOff` methods.

```javascript
switchInstance.onTurnedOn(() => console.log('Switch is now ON'));
switchInstance.onTurnedOff(() => console.log('Switch is now OFF'));
```

### Removing the Switch
Remove the switch from the DOM using the `remove` method when it is no longer needed.

```javascript
switchInstance.remove();
```



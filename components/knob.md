---
title: Knob
parent: Components
nav_order: 9
---

# The Knob Component

The `Knob` component provides an interface to interact with a customizable knob element.


## Creating a Knob

To create a knob, instantiate the `Knob` class with configuration parameters.

```javascript

// Example configuration
const config = {
    min: 0,
    max: 100,
    size: 150,
    initialValue: 50,
    knobColor: '#333',
    valueColor: '#fff',
    style: {
        position: 'absolute',
        top: '50px',
        left: '50px',
    }
};

const knobInstance = new Protobject.Knob(config);
```

## Setting Knob Color
Change the knob and value display colors dynamically using the `setKnobColor` method.

```javascript

knobInstance.setKnobColor({
    background: 'red',
    value: 'white'
});
```

## Customizing Styles
Customize the knob container style using the `setStyle` method.

```javascript

knobInstance.setStyle({
    background: 'grey',
    borderRadius: '10px',
    boxShadow: '0 0 5px rgba(0,0,0,0.5)'
});
```

## Setting Position
Adjust the position of the knob using the `setPosition` method.

```javascript

knobInstance.setPosition(100, 200);
```

## Handling Value Changes
Register a callback function to be called when the knob value changes using the `onChange` method.

```javascript

knobInstance.onChange((value) => {
    console.log('Knob value changed to: '+ value);
});
```

## Removing the Knob
Remove the knob from the DOM when it is no longer needed using the `remove` method.

```javascript
knobInstance.remove();
```



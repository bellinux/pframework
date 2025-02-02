---
title: Lamp
parent: Components
nav_order: 2
---

# The Lamp Component

The Lamp class is a JavaScript utility designed to create a customizable lamp-like element with a default or user-defined style. It allows you to set the color and style of the lamp and remove it when needed.

## Creating a Lamp
 
To create a lamp, instantiate the `Lamp` class with an optional style object.

```javascript

const lamp = new Protobject.Lamp({
    width: '200px',
    height: '200px',
    top: '50px',
    left: '50px',
});


```


## Setting Lamp Color
To set the color of the lamp, use the `setColor` method. You can pass either a string representing the color or an object with `r`, `g`, and `b` properties.

```javascript
// Using a color string
lamp.setColor('red');

// Using an RGB object
lamp.setColor({ r: 255, g: 0, b: 0 });

```

## Customizing Lamp Style
To customize the style of the lamp, use the `setStyle` method. Pass an object with the desired CSS properties.

```javascript

lamp.setStyle({
    borderRadius: '50%',
    boxShadow: '0 0 10px rgba(0, 0, 0, 0.5)'
});
```

## Removing the Lamp
To remove the lamp, use the `remove` method.

```javascript
lamp.remove();
```

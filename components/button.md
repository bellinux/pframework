---
title: Button
parent: Components
nav_order: 1
---

# The Button Component

The `Button` component creates a customizable button element with event listeners for both touch and mouse events. This component allows you to easily create, style, and manage buttons in your applications.

## Creating a Button
To create a button, instantiate the Button class with an options object. You can specify the text, event handlers, and styles.

```javascript
const button = new Protobject.Button({
    text: 'Click Me',
    style: {
        backgroundColor: 'blue',
        color: 'white',
        padding: '10px 20px'
    }
});

```

## Setting Button Text

To set the text of the button after it has been created, use the `setText` method.

```javascript
button.setText('New Text');
```


## Setting Button Position
To set the position of the button, use the `setPosition` method.

```javascript
button.setPosition('100px', '50px');
```

## Customizing Button Style
To customize the style of the button, use the `setStyle` method. Pass an object with the desired CSS properties.

```javascript

button.setStyle({
    backgroundColor: 'green',
    borderRadius: '5px'
});
```

## Handling Button Events
To handle button press and release events, use the `onPressed` and `onRelease` methods to set the respective callbacks.

```javascript
button.onPressed(() => console.log('Button pressed'));
button.onRelease(() => console.log('Button released'));
```

## Removing the Button
To remove the button from the document, use the `remove` method.

```javascript
button.remove();
```






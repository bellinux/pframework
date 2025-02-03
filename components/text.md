---
title: Text 
parent: Components
nav_order: 19
---

# The Text Component

The `Text` component provides a flexible and customizable text interface. It allows setting various properties like placeholder, default text, editable state, and style. It also supports handling text input events through a callback function.



## Creating a Text Component
To create a Text component, instantiate it with the desired configuration options.

```javascript
const myText = new Protobject.Text({
    placeholder: 'Enter your message...',
    defaultText: '',
    editable: true,
    style: {
        backgroundColor: 'lightyellow',
        border: '1px solid black'
    },
    onInput: (text) => {
        console.log(`Text Input: ${text}`);
    }
});

```

## Setting Properties
You can set various properties of the Text component after creation.

```javascript
//Set Text
myText.setText('New text content');

//Set Editable
myText.setEditable(false); // Makes the text input read-only

//Set Placeholder
myText.setPlaceholder('New placeholder text');

//Set Position
myText.setPosition('100px', '50px');

//Set Style
myText.setStyle({
    backgroundColor: 'lightblue',
    color: 'darkblue'
});

```

## Handling Text Input
To handle the text input event, set a callback function using the onInput method. This callback function will be called with the text content whenever it changes.

```javascript

myText.onInput((text) => {
    console.log(`Updated Text: ${text}`);
});

```

## Getting Text
To retrieve the current text content of the Text component, use the getText method.

```javascript
const currentText = myText.getText();
console.log(`Current Text: ${currentText}`);
```

## Removing the Text Component
To remove the Text component from the document, use the remove method.

```javascript
myText.remove();
```
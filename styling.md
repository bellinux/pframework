---
title: Styling
nav_order: 5
---

# Styling the Connect Button

By default, the connect button only shows a (+) sign. You can customize it further by adding the following CSS to the main page:

```css
#ProtobjectPlusButton {
    width: 80px !important;
}

#ProtobjectPlusButton:after {
    content: ' Connect';
}
```

Feel free to experiment and add your own styling. 

# Tips for Customizing the Connect Button

When customizing the connect button, consider the following:

- **Change the Button Size**:  
  Adjust the button’s width and height to fit the icon properly. Use CSS properties like `width` and `height` to control the button’s dimensions. If needed, use `!important` to ensure the styles are applied when the CSS is inline.

- **Add an Icon Using Background**:  
  You can add an icon by setting a `background-image` on the button. Ensure the icon fits well by using `background-size: contain` or `cover`.

- **Make Text Transparent**:  
  If you are adding an icon via the `background-image` property, make the text transparent using `color: transparent` or remove the text entirely, as the default "+" sign may conflict with the icon.

- **Adjust Icon Positioning**:  
  Use `background-position` to control where the icon is positioned within the button. Common values include `center`, `top`, or `left`, depending on where you want the icon to appear.

- **Icon Size**:  
  Use `background-size` to scale the icon. You can set it to `contain` (to maintain aspect ratio) or a specific pixel size to better fit your design.

- **Styling Button's Appearance**:  
  You can change the background of the button (e.g., gradient, color, etc.), apply `border-radius` for rounded corners, adjust padding for spacing, and modify text styles for further customization.

- **Use `!important` When Needed**:  
  Since the CSS might be inline, use `!important` to override default styles and ensure your custom styles are applied correctly.

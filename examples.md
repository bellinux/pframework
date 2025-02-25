---
title: Example Projects
nav_order: 7
---

# Example Projects

Browse these examples to discover what you can create with the Protobject Framework.
{: .fs-6 .fw-300 }












---

{% include video_embed.html video_id="Mv5B-Sr4Vtk" %}

By moving a small house to simulate earthquakes of different intensities, the system identifies the real earthquake that most closely matches the generated movement. Additionally, clicking on an earthquake causes a house to move—and potentially collapse—depending on the earthquake's intensity.  

## How It Works  

- `index.html` displays the visualization.  
- `movement.html` detects the movement of a small house, where an internal smartphone registers motion.  
- `arduino.html` controls the motor that moves the house in response to selected earthquakes.  

This setup allows users to explore the relationship between earthquake intensity and structural impact interactively.

[Open on Glitch](https://glitch.com/edit/#!/infovis-terremotos){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 target="_blank"}













---

{% include video_embed.html video_id="fLIPH9yM_C0" %}

In a closed space with active heating, the temperature remains stable thanks to a regulation system. However, when a door is opened, accumulated heat starts to escape while cold air enters, leading to a temperature drop.  

The rate of this decrease may depend on the degree of door opening: the wider the door is open, the faster the temperature drops. Conversely, if the door is only slightly open, the temperature decrease will be slower.  

## How It Works  

- `index.html` displays the visualization.  
- `door.html` detects the degree of door opening.  

Based on this data, the visualization dynamically represents how the temperature changes in response to different door positions.

[Open on Glitch](https://glitch.com/edit/#!/infovis-door-heater){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 target="_blank"}















---

{% include video_embed.html video_id="KncN6g7VSN8" %}

This system controls the visualization of a graph displaying the export data of products, such as beans, tea, and tuna, in various countries. The graph is dynamically updated based on actions like adding, removing, or rearranging these products in the scene.  

## How It Works  

- `index.html` displays the graph visualization.  
- `order.html` tracks the order of the products in the scene.  

Changes in the arrangement of the products affect the data displayed on the graph, reflecting their export trends across different countries.



[Open on Glitch](#){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 target="_blank"}
























---

{% include video_embed.html video_id="99EEUrqvUGY" %}

The visualization dynamically adjusts based on body movement and position. The zoom level changes depending on the distance: the closer you are, the more zoomed-in the view, while stepping back decreases the zoom. Additionally, moving left or right shifts the visualization accordingly.  

## How It Works  

- `index.html` displays the visualization.  
- `body.html` detects body movement, including distance and position.  

This interaction allows users to navigate and explore the visualization using only their body movements.  

[Open on Glitch](https://glitch.com/edit/#!/infovis-body-zoom){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 target="_blank"}





































---

{% include video_embed.html video_id="rzjwasJGIOk" %}

This system displays different Bitcoin price predictions—optimistic, neutral, and pessimistic—based on various inputs such as gestures, facial expressions, and interaction with physical objects.  

## How It Works  

- `index.html` displays the main prediction graph.  
- `hand.html` tracks hand gestures to influence predictions.  
- `face.html` detects facial expressions to adjust predictions.  
- `inclination.html` monitors interactions with physical objects, affecting the predictions.  

These pages work together to dynamically generate predictions based on user interactions across multiple input modes.

[Open on Glitch](https://glitch.com/edit/#!/infovis-bitcoin-predictions){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 target="_blank"}







---

{% include video_embed.html video_id="gUj_jpRxgCU" %}

This project dynamically adjusts the displayed data based on the number of people present. For instance, it can illustrate how electricity consumption varies depending on the number of residents in a household.

## How It Works

- `index.html` displays the visualization.  
- `persondetector.html` detects the number of people in front of the display.  

Based on the detected count, different data sets are presented to reflect relevant variations.

[Open on Glitch](https://glitch.com/edit/#!/infovis-consumption-persons){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 target="_blank"}











---

{% include video_embed.html video_id="a000BBFkAHc" %}

This system allows users to interact with a physical map. By touching different regions of the map, the amount in millions of dollars of fruit exports from the selected country is heard.  

## How It Works  

- `index.html` displays the graph showing the export data.  
- `hand.html` detects the position of the user's hand on the map.  

The system links the hand's position on the map with the corresponding export data, providing auditory feedback based on the selected country's fruit export figures.



[Open on Glitch](#){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 target="_blank"}









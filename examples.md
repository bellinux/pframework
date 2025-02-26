---
title: Example Projects
nav_order: 7
---

# Example Projects

Browse these examples to discover what you can create with the Protobject Framework.
{: .fs-6 .fw-300 }


[DataViz Projects](#dataviz-projects){: .btn .fs-5 .mb-4 .mb-md-0 .mr-2}
[Ubicomp Projects](#ubicomp-projects){: .btn .fs-5 .mb-4 .mb-md-0 .mr-2}

---

## DataViz Projects
In these projects, data visualization serves as the context for prototyping interactive systems that combine physical and digital elements. The focus is on creating prototypes that allow users to engage with data through tangible interactions—whether by moving objects, performing gestures, or interacting with physical maps.



{% include video_embed.html video_id="Mv5B-Sr4Vtk" %}

By moving a small house to simulate earthquakes of different intensities, the system identifies the real earthquake that most closely matches the generated movement. Additionally, clicking on an earthquake causes a house to move—and potentially collapse—depending on the earthquake's intensity.  

How it works:
- `index.html` displays the visualization.  
- `movement.html` detects the movement of a small house, where an internal smartphone registers motion.  
- `arduino.html` controls the motor that moves the house in response to selected earthquakes.  

This setup allows users to explore the relationship between earthquake intensity and structural impact interactively.

[Open on Glitch](https://glitch.com/edit/#!/infovis-terremotos){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 target="_blank"}













---

{% include video_embed.html video_id="fLIPH9yM_C0" %}

In a closed space with active heating, the temperature remains stable thanks to a regulation system. However, when a door is opened, accumulated heat starts to escape while cold air enters, leading to a temperature drop.  

The rate of this decrease may depend on the degree of door opening: the wider the door is open, the faster the temperature drops. Conversely, if the door is only slightly open, the temperature decrease will be slower.  

How it works:
- `index.html` displays the visualization.  
- `door.html` detects the degree of door opening.  

Based on this data, the visualization dynamically represents how the temperature changes in response to different door positions.

[Open on Glitch](https://glitch.com/edit/#!/infovis-door-heater){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 target="_blank"}















---

{% include video_embed.html video_id="KncN6g7VSN8" %}

This system controls the visualization of a graph displaying the export data of products, such as beans, tea, and tuna, in various countries. The graph is dynamically updated based on actions like adding, removing, or rearranging these products in the scene.  

How it works:
- `index.html` displays the graph visualization.  
- `order.html` tracks the order of the products in the scene.  

Changes in the arrangement of the products affect the data displayed on the graph, reflecting their export trends across different countries.



[Open on Glitch](https://glitch.com/edit/#!/infovis-orderding-products){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 target="_blank"}
























---

{% include video_embed.html video_id="99EEUrqvUGY" %}

The visualization dynamically adjusts based on body movement and position. The zoom level changes depending on the distance: the closer you are, the more zoomed-in the view, while stepping back decreases the zoom. Additionally, moving left or right shifts the visualization accordingly.  

How it works:
- `index.html` displays the visualization.  
- `body.html` detects body movement, including distance and position.  

This interaction allows users to navigate and explore the visualization using only their body movements.  

[Open on Glitch](https://glitch.com/edit/#!/infovis-body-zoom){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 target="_blank"}





































---

{% include video_embed.html video_id="rzjwasJGIOk" %}

This system displays different Bitcoin price predictions—optimistic, neutral, and pessimistic—based on various inputs such as gestures, facial expressions, and interaction with physical objects.  

How it works:
- `index.html` displays the main prediction graph.  
- `hand.html` tracks hand gestures to influence predictions.  
- `face.html` detects facial expressions to adjust predictions.  
- `inclination.html` monitors interactions with physical objects, affecting the predictions.  

These pages work together to dynamically generate predictions based on user interactions across multiple input modes.

[Open on Glitch](https://glitch.com/edit/#!/infovis-bitcoin-predictions){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 target="_blank"}







---

{% include video_embed.html video_id="gUj_jpRxgCU" %}

This project dynamically adjusts the displayed data based on the number of people present. For instance, it can illustrate how electricity consumption varies depending on the number of residents in a household.

How it works:
- `index.html` displays the visualization.  
- `persondetector.html` detects the number of people in front of the display.  

Based on the detected count, different data sets are presented to reflect relevant variations.

[Open on Glitch](https://glitch.com/edit/#!/infovis-consumption-persons){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 target="_blank"}











---

{% include video_embed.html video_id="a000BBFkAHc" %}

This system allows users to interact with a physical map. By touching different regions of the map, the amount in millions of dollars of fruit exports from the selected country is heard.  


How it works:
- `index.html` displays the graph showing the export data.  
- `hand.html` detects the position of the user's hand on the map.  

The system links the hand's position on the map with the corresponding export data, providing auditory feedback based on the selected country's fruit export figures.



[Open on Glitch](https://glitch.com/edit/#!/infovis-finger-interaction){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 target="_blank"}



## Ubicomp Projects

In these projects, interactive systems are prototyped to explore the integration of physical and digital elements in real-world applications. The focus is on developing functional prototypes that respond to environmental inputs—such as movement, sound, posture, or user presence—through tangible interactions. 


{% include video_embed.html video_id="HfbwzE8pQpQ" %}

This system detects unauthorized entry into a room and triggers an alarm if no deactivation code is entered.  

How it works:
- `index.html` manages the control panel for the alarm.  
- `sensor.html` handles the motion sensor that activates the alarm.  

This system detects motion within a room and starts a countdown. During this period, users can enter a code to deactivate the alarm. If no code is provided, an alert is triggered to notify occupants of the intrusion.

[Open on Glitch](https://glitch.com/edit/#!/smart-device-alarm-system){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 target="_blank"}



---

{% include video_embed.html video_id="EVoAY_iS0VM" %}

This system promotes silence in classrooms by displaying a noise alert when sound levels exceed a specified threshold.  

How it works:
- `index.html` detects the noise level and activates the corresponding indicator using a lamp.  

This system monitors noise levels in a classroom and displays a visual alert when the sound exceeds a predefined threshold. The alert serves as a cue to encourage a quieter environment conducive to learning. 

[Open on Glitch](https://glitch.com/edit/#!/smart-device-noise-indicator){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 target="_blank"}



---

{% include video_embed.html video_id="NSRCxqlIvWU" %}

This prototype helps users maintain proper posture by vibrating whenever bad posture is detected.  

How it works:
- `index.html` manages the tilt sensor placed on the shoulders.  
- `control.html` handles device activation and sensitivity adjustment.  

This system detects improper posture and provides haptic or visual feedback to alert the user. A control interface allows for adjusting sensitivity or temporarily pausing the alerts.

[Open on Glitch](https://glitch.com/edit/#!/smart-device-posture){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 target="_blank"}


---

{% include video_embed.html video_id="nRb_IDX4cvc" %}

This prototype optimizes energy usage by controlling lights based on user presence.  

How it works:
- `index.html` manages the Arduino to move the light switches.  
- `sensor1.html` detects movement in one specific area.  
- `sensor2.html` detects movement in another specific area.  

This system detects user movement and automatically controls lighting to optimize energy usage. Lights are activated in occupied areas and turned off in unoccupied spaces.

[Open on Glitch](https://glitch.com/edit/#!/smart-device-light-system){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 target="_blank"}


---

{% include video_embed.html video_id="S0D4vLfPK9k" %}

This system secures access to a door through a customizable code input mechanism.  

How it works:
- `index.html` handles the PIN code input.  
- `control.html` manages the Arduino to lock and unlock the door.  
- `remote.html` provides a master key feature for unlocking or resetting the code.  

This system secures access to a door by using a customizable code input. The door lock is controlled by entering a numeric combination, with the option to reset the code using a Master Key feature.

[Open on Glitch](https://glitch.com/edit/#!/smart-device-lock){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 target="_blank"}

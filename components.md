---
title: Components
nav_order: 10
has_toc: false
---

# Available Components

Protobject Framework offers a wide range of components that enable the creation of interactive, distributed, and dynamic systems. These components can be used across various devices, such as smartphones, tablets, and PCs, to prototype advanced interactive systems. Each component serves a specific function, from simple user interface elements like buttons and switches to more advanced sensors and actuators like cameras, accelerometers, and sound players. By combining these components, users can rapidly build systems that interact with both the physical and digital worlds.
{: .fs-6 .fw-300 }

---

We categorize and describe the 24 available components based on their primary functionality and corresponding physical equivalents as follows:

## Camera-Based Components

These components rely on camera input to detect and process visual data, enabling applications in motion tracking, and gesture recognition.

1. [**PresenceSensor**](components/presenceSensor.md): Monitors presence by comparing the current camera image with a baseline, detecting changes. It corresponds to a camera motion sensor with a fixed baseline.
    
2. [**LightSensor**](components/lightSensor.md): Monitors brightness levels using the camera, providing real-time updates. It corresponds to a light sensor.
    
3. [**CameraMovement**](components/cameraMovement.md): Detects camera-based motion by calculating the direction and magnitude of movement using optical flow. It corresponds to a camera motion sensor.

4. [**ArUco**](components/aruco.md): Detects ArUco markers using the camera, providing real-time updates on marker position and size. This feature can be used for tracking physical objects.

5. [**HandSensor**](components/handSensor.md): Detects hands using the camera, tracking landmarks and gestures with real-time updates.

6. [**BodySensor**](components/bodySensor.md): Detects human bodies using the camera, tracking body landmarks and features.

7. [**FaceSensor**](components/faceSensor.md): Detects faces using the camera, tracking facial landmarks and expressions.

8.  [**QR**](components/qr.md): Scans and decodes QR codes using the camera, providing the embedded data through a callback. It corresponds to a QR code reader.

## Microphone-Based Components

These components use audio input from a microphone to process sound data for classification, noise detection, or speech recognition.

8. [**NoiseSensor**](components/noiseSensor.md): Detects noise intensity in the environment and corresponds to a noise sensor.
    
9. [**VoiceRecognition**](components/voiceRecognition.md): Converts spoken words into text, enabling voice-controlled interactions. It corresponds to a microphone with an AI-based voice recognition engine.
    
10. [**AudioClassifier**](components/audioClassifier.md): Classifies audio inputs using the microphone, detecting and categorizing sounds with real-time updates. It corresponds to an AI-enabled microphone sound detector.

## Speaker-Based Components

These components utilize audio output via speakers, enabling music playback, sound synthesis, or speech generation.

11. [**SoundPlayer**](components/soundPlayer.md): Plays and controls audio playback, offering methods for play, pause, volume adjustment, and looped playback. It corresponds to a speaker for music reproduction.
    
12. [**NotePlayer**](components/notePlayer.md): Plays musical notes using preloaded instrument samples, supporting dynamic note playback. It corresponds to a speaker reproducing tones.
    
13. [**TextToSpeech**](components/textToSpeech.md): Converts text into speech, supporting multiple languages. It corresponds to a speaker reproducing voice.

## Motion and Orientation Sensors

These components leverage motion-related sensors, such as accelerometers and gyroscopes, to provide data on movement, orientation, and tilt.

14. [**Acceleration**](components/acceleration.md): Provides access to accelerometer data, enabling motion interaction through X, Y, and Z-axis values. It corresponds to an accelerometer, excluding the effects of gravity.
    
15. [**Inclination**](components/inclination.md): Tracks device tilt or angle relative to the ground, providing X, Y, and Z-axis inclination data. It corresponds to an accelerometer, including the effects of gravity.
    
16. [**Orientation**](components/orientation.md): Provides orientation data from a device’s sensors. It corresponds to a fusion of magnetometer, accelerometer, and gyroscope sensors.

## Interactive Components

These components enable interactive user input or output, simulating physical devices such as switches, knobs, and displays.

17. [**Lamp**](components/lamp.md): A customizable visual element that represents a lamp, with adjustable size, position, color, and style. It corresponds to an LED or lamp.

18. [**Switch**](components/switch.md): A customizable interactive switch with configurable labels and styles, designed for toggle-based actions in control interfaces or settings. It corresponds to an On/Off switch.

19. [**Button**](components/button.md): A customizable element designed to detect touch, featuring adjustable appearance and behavior through CSS. It corresponds to a touch sensor.

20. [**Knob**](components/knob.md): Provides interaction with a customizable knob element, allowing adjustment of properties such as size, color, and value. It corresponds to a potentiometer.
    
21. [**Text**](components/text.md): Provides a customizable text interface, with or without an editable state. It is useful for interactive input fields and corresponds to an LCD display.

## Miscellaneous Components

These components provide unique functionalities that do not fall into the previously defined categories.

22. [**Haptic**](components/haptic.md): Controls device vibration with customizable patterns, providing tactile feedback. It corresponds to a vibrotactile actuator.
    
23. [**GPS**](components/gps.md): Provides geolocation data, including latitude, longitude, and speed, with real-time updates. It corresponds to a GPS module.
    
24. [**Arduino**](components/arduino.md): Enables communication with Arduino Leonardo devices via WebUSB, allowing for control of pins and interaction with sensors. It is ideal for extending platform capabilities for physical actuation using servos or for utilizing sensing capabilities not possible with smartphones.

25. [**NFC**](components/nfc.md): Interacts with Near Field Communication (NFC) tags, allowing the reading of a tag's unique serial number. It corresponds to an NFC reader.

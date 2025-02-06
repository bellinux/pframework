---
title: Arduino 
parent: Components
nav_order: 17
---

# The Arduino Component

The `Arduino` component provides an interface for connecting to and communicating with an Arduino Leonardo device via WebUSB. It allows setting callback functions to handle incoming data, as well as sending commands to control the Arduino's pins.


## Programming Arduino Leonardo
Protobject is compatible with the Arduino Leonardo only, which must be programmed using the following code. 
If you're not familiar with WebUSB, follow [this guide](https://github.com/webusb/arduino).

```c
#include <Servo.h>
#include <WebUSB.h>
#include <ArduinoJson.h>

WebUSB WebUSBSerial(1 /* https:// */, "");
#define Serial WebUSBSerial

Servo rservo;
Servo lservo;
int defaultL = 1500;
int defaultR = 1500;
DynamicJsonDocument dynamicJSONDocument(128);

void setup() {
  while (!Serial) {
    ;
  }
  Serial.begin(9600);
  Serial.write("Sketch begins.\r\n> ");
  Serial.flush();
  lservo.attach(5); 
  rservo.attach(6); 
  pinMode(7, INPUT);
  pinMode(8, INPUT);
  pinMode(9, INPUT);
  pinMode(3, OUTPUT); 
  pinMode(11, OUTPUT); 
  pinMode(13, OUTPUT); 
  rservo.writeMicroseconds(defaultR);
  lservo.writeMicroseconds(defaultL);  
}

void loop() {
  const auto deser_err = deserializeJson(dynamicJSONDocument, Serial);
  if (!deser_err){
      JsonObject obj = dynamicJSONDocument.as<JsonObject>();
      if (obj["device"] == "robot") { //and servos in general, continuous and angular
        int rightSpeed = obj["right"];
        int leftSpeed = obj["left"];
        rservo.writeMicroseconds(defaultR-rightSpeed);
        lservo.writeMicroseconds(defaultL+leftSpeed);
      }
      if (obj["device"] == "digitalWrite") { //pins 3,11,13
        int pin = obj["pin"];
        int val = obj["val"];
        if (val==1){
          digitalWrite(pin, HIGH);
        } else {
          digitalWrite(pin, LOW);
        }
        
      }
      if (obj["device"] == "analogWrite") { //pins 3,11,13
        int pin = obj["pin"];
        int val = obj["val"];
        analogWrite(pin, val);
      }
      if (obj["device"] == "readAll") { //digital 7,8,9 //analog 0,1,2
        StaticJsonDocument<200> doc;
        doc["d7"] = digitalRead(7);
        doc["d8"] = digitalRead(8);
        doc["d9"] = digitalRead(9);
        doc["a0"] = analogRead(0);
        doc["a1"] = analogRead(1);
        doc["a2"] = analogRead(2);
        serializeJson(doc, Serial);
        Serial.flush();
      }
    }
}

```

Once programmed, you can connect the Arduino Leonardo to any PC or smartphone via USB. No Arduino IDE is required to work with it.

## Starting the Arduino Component
To start connecting to an Arduino device, call the start method. This will display a popup for the user to confirm the connection.

```javascript
Protobject.Arduino.start();
```

## Handling Arduino Data
To handle data received from the Arduino, set a callback function using the onData method. This callback function will be called with the data whenever it is received.

```javascript
Protobject.Arduino.onData((data) => {
    console.log('Received data:', data);
});

```
It receives data from a0, a1, a2 and d7, d8, d9.

## Sending Commands to Arduino
You can send various commands to the Arduino to control its pins.

### Digital Write
To set the value of a digital pin:

```javascript
Protobject.Arduino.digitalWrite({ pin: 3, value: 1 }); // Sets pin 3 to HIGH
```

Valid pins are 3, 11 and 13.

### Analog Write
To set the value of an analog pin:

```javascript
Protobject.Arduino.analogWrite({ pin: 3, value: 128 }); // Sets pin 3 to a PWM value of 128
```

Valid pins are 3, 11 and 13.

### Servo Write
To set the value of a servo motor connected to pin 5 or 6:

```javascript
Protobject.Arduino.servoWrite({ pin: 5, value: 500 }); // Sets servo on pin 5 to 500 (see writeMicroseconds)
//https://www.arduino.cc/reference/en/libraries/servo/writemicroseconds/

```

### Continuous Servo Write
To set the value of a continuous servo motor connected to pin 5 or 6:

```javascript
Protobject.Arduino.contServoWrite({ pin: 5, value: 500 }); // Sets servo on pin 5 to 500 (see writeMicroseconds)
//https://www.arduino.cc/reference/en/libraries/servo/writemicroseconds/

```

## Usage Example

```javascript

Protobject.Arduino.start();
Protobject.Arduino.onData((data) => {
    console.log('Received data:', data);
});

let myButton = new Protobject.Button();

myButton.onPressed(function(){
  Arduino.digitalWrite({ pin: 13, value: 1 }); // Sets pin 13 to HIGH
})

myButton.onRelease(function(){
  Arduino.digitalWrite({ pin: 13, value: 0 }); // Sets pin 13 to LOW
})
```

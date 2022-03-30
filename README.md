# ESP32IoTController

## Table of Contents
1. [Overview](#Overview)
1. [Product Spec](#Product-Spec)
1. [Wireframes](#Wireframes)
2. [Schema](#Schema)

## Overview
### Description
(Senior Design II project) An Android-native mobile app that enables user to monitor the sensors (temperature, pH, moisture) and control the actuators (grow lights, fans, water pump) of an ESP32 LoRaWAN-enabled semi-autonomous greenhouse.

### App Evaluation
[Evaluation of your app across the following attributes]
- **Category:** IoT
- **Mobile:** This app would be primarily developed for mobile but would perhaps be just as viable on a computer. Functionality wouldn't be limited to mobile devices.
- **Story:** Monitor the sensors (temperature, pH, moisture) and control the actuators (grow lights, fans, water pump) of an ESP32 LoRaWAN-enabled semi-autonomous greenhouse over the MQTT communication protocol.
- **Market:** Any individual could choose to use this app to control their smart greenhouse.
- **Habit:** This app could be used as often or unoften as the user wanted to monitor and/or control their greenhouses' conditions.
- **Scope:** Instructions on how to download the app and pair it to a smart greenhouse would come include with any unit sold.

## Product Spec

### 1. User Stories (Required and Optional)

**Required Must-have Stories**

* [fill in your required user stories here]
  
  [] Sensor values update regularly.
  
  [] Actuator controls are responsive within the app.
  
  [] Actuator controls provoke a response within the IoT device.
  
* ...

**Optional Nice-to-have Stories**

* [fill in your required user stories here]
  
  [] App sends notifications to user of latest updates. (ie. "The water tank is empty - please refill!")
* ...

### 2. Screen Archetypes

* Hub Screen
    * Welcome message, sensor activity, actuator slidebars, a binary switch, and (optional) last text notification.
      * ...

### 3. Navigation

**Tab Navigation** (Tab to Screen)

* n/a

**Flow Navigation** (Screen to Screen)

* n/a

## Wireframes
[Add picture of your hand sketched wireframes in this section]
### [BONUS] Digital Wireframes & Mockups

"<blockquote class="imgur-embed-pub" lang="en" data-id="M3KK1OO"><a href="https://imgur.com/M3KK1OO">View post on imgur.com</a></blockquote>



### [BONUS] Interactive Prototype

## Schema
[This section will be completed in Unit 9]
### Models

| Property              | Type          | Description   |
| --------------------- | ------------- | ------------- | 
| Moist_Sens            | Number        | real-time moisture sensor reading  |
| Temp_Sens             | Number        | real-time thermometer sensor reading  |
| Light_Sens            | Binary        | real-time grow light actuator ON/OFF reading  |
| pH_Sens               | Number        | real-time pH sensor reading  |
| Slider1               | Number        | UI slider for fan control  |
| Temp_Ctrl             | Number        | returns slider value for fan control  |
| Slider2               | Number        | UI slider for water pump control   |
| Moist_Ctrl            | Number        | returns slider value for water pump control  |
| Light_Ctrl            | Binary        | ON/OFF grow light control switch  |
| Light_Sens1           | Number        | set slider value for grow light control  |
| Alert_Sens            | String        | returns latest notification  |
| Status_Chnl           | Server Component  | provides functions for HTTP GET, POST, PUT and DELETE requests  |
| Temp_Ctrl_Chnl        | Server Component  | provides functions for HTTP GET, POST, PUT and DELETE requests  |
| Moist_Ctrl_Chnl       | Server Component  | provides functions for HTTP GET, POST, PUT and DELETE requests  |
| Light_Ctrl_Chnl       | Server Component  | provides functions for HTTP GET, POST, PUT and DELETE requests  |
| Clock1                | Number        | reads microcontroller every 2 seconds  |

### Networking
- [Add list of network requests by screen ]
- [Create basic snippets for each Parse network request]
- [OPTIONAL: List endpoints if using existing API such as Yelp]

/********* Control actuators *************/
void takeActions(void)
{
  Serial.print("Pump: ");
  Serial.println(pump);
  Serial.print("Lamp: ");
  Serial.println(lamp);
  if (pump == 1) digitalWrite(ACTUATOR1, LOW);
  else digitalWrite(ACTUATOR1, HIGH);
  if (lamp == 1) digitalWrite(ACTUATOR2, LOW);
  else digitalWrite(ACTUATOR2, HIGH);
}
/********* Read actuators *************/
int readThingSpeak(String channelID)
{
  startThingSpeakCmd();
  int command;

  String getStr = "GET /channels/";
  getStr += channelID;
  getStr +="/fields/1/last";
  getStr += "\r\n";
  String messageDown = sendThingSpeakGetCmd(getStr);
  if (messageDown[5] == 49)
  {
    command = messageDown[7]-48; 
    Serial.print("Command received: ");
    Serial.println(command);
  }
  else command = 9;
  return command;
}

Write to actuators via API calls example:
Turn on actuator 1:
https://api.thingspeak.com/update?api_key=ACT1_WRITE_KEY&field1=1

Turn off actuator 1:
https://api.thingspeak.com/update?api_key=ACT1_WRITE_KEY&field1=0

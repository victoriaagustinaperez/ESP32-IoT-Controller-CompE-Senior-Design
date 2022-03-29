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

<img src="<blockquote class="imgur-embed-pub" lang="en" data-id="M3KK1OO"><a href="https://imgur.com/M3KK1OO">View post on imgur.com</a></blockquote><script async src="//s.imgur.com/min/embed.js" charset="utf-8"></script>" width=600>



### [BONUS] Interactive Prototype

## Schema
[This section will be completed in Unit 9]
### Models

| Property              | Type          | Description   |
| --------------------- | ------------- | ------------- | 
| VerticalArrangement1  | Content Cell  | Content Cell  |
| Label 1               | Content Cell  | Content Cell  |
| SENSORS               | Content Cell  | Content Cell  |
| TableArrangement1     | Content Cell  | Content Cell  |
| Label2                | Content Cell  | Content Cell  |
| Label3                | Content Cell  | Content Cell  |
| Moist_Sens            | Content Cell  | Content Cell  |
| Label6                | Content Cell  | Content Cell  |
| Light_Sens            | Content Cell  | Content Cell  |
| Label13               | Content Cell  | Content Cell  |
| pH_Sens               | Content Cell  | Content Cell  |
| SPACE                 | Content Cell  | Content Cell  |
| ACTUATORS             | Content Cell  | Content Cell  |
| SPACE1                | Content Cell  | Content Cell  |
| TableArrangement2     | Content Cell  | Content Cell  |
| Label8                | Content Cell  | Content Cell  |
| Slider1               | Content Cell  | Content Cell  |
| Temp_Ctrl             | Content Cell  | Content Cell  |
| Label9                | Content Cell  | Content Cell  |
| Slider2               | Content Cell  | Content Cell  |
| Moist_Ctrl            | Content Cell  | Content Cell  |
| Label10               | Content Cell  | Content Cell  |
| Light_Ctrl            | Content Cell  | Content Cell  |
| Light_Sens1           | Content Cell  | Content Cell  |
| Label11               | Content Cell  | Content Cell  |
| Label12               | Content Cell  | Content Cell  |
| ALERTS                | Content Cell  | Content Cell  |
| Alert_Sens            | Content Cell  | Content Cell  |
| Status_Chnl           | Content Cell  | Content Cell  |
| Temp_Ctrl_Chnl        | Content Cell  | Content Cell  |
| Moist_Ctrl_Chnl       | Content Cell  | Content Cell  |
| Light_Ctrl_Chnl       | Content Cell  | Content Cell  |
| Clock1                | Content Cell  | Content Cell  |
| Clock2                | Content Cell  | Content Cell  |

### Networking
- [Add list of network requests by screen ]
- [Create basic snippets for each Parse network request]
- [OPTIONAL: List endpoints if using existing API such as Yelp]

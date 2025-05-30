---
title: BEEWATCH-MK2 Part 1 -Story
date: 2025-02-13 07:20:00 +530
categories: [Homelab, Project]
tags: [gps, watch, esp32]
comments: true
mermaid: true
math: true
image:
    path: https://i.postimg.cc/ht93r9VV/V2.png
    lqip: https://i.postimg.cc/ht93r9VV/V2.png
    alt: BEEWATCH MK1
---

## Story

I started trying to make watch prototypes in 2015. My first watch prototype was a complete copy of the code and hardware I found online. At the time, I was just starting my engineering journey, and it was built using an Arduino Nano.

Four years later, I wanted to create a watch that could fit on a single board. That’s when I started working on the **BEEWATCH MK1**.


### BEEWATCH MK1

![BEEWATCH MK1 breadboard prototype](https://i.postimg.cc/hv3dL73x/BEEWATCH-MK1.gif){: lqip="https://i.postimg.cc/hv3dL73x/BEEWATCH-MK1.gif"}
_BEEWATCH MK1 breadboard prototype_

I started this project with a breadboard prototype.

For this project, my inspirations were:
- [Zak's DIY digital wristwatch](https://blog.zakkemble.net/diy-digital-wristwatch/)
- Circuit State's [ISL1208 RTC tutorial](https://www.circuitstate.com/tutorials/interfacing-intersil-isl1208-rtc-with-arduino/)

I chose the ISL1208 RTC because the article helped me understand how RTCs function. While experimenting with the library, I discovered a bug: the weeks were not updating. I contacted the CEO of Circuit State, Vishnu Mohan, who encouraged me to fix it. At the time, I didn’t have much confidence in working with libraries—I had only created small libraries for my projects. However, I decided to give it a try. If I remember correctly, it took me about a week to find and fix the issue. It was a fantastic learning experience for me.

The BEEWATCH MK1 PCBA was ready after two iterations. However, there was a problem with the OLED display: it would stop working after about a minute. Strange, right? I spent time debugging and realized the issue was related to the charge pump capacitors. Unfortunately, I couldn’t resolve it at the time. I eventually lost interest and didn’t have the time to debug further. Still, I hold onto the dream of wearing my own watch, it would make me incredibly proud 😌.

![BEEWATCH MK1 REV1](https://i.postimg.cc/Nj9QfPqB/V1.png){: lqip="https://i.postimg.cc/Nj9QfPqB/V1.png"}
_BEEWATCH MK1 REV1_

![BEEWATCH MK1 REV2](https://i.postimg.cc/ht93r9VV/V2.png){: lqip="https://i.postimg.cc/ht93r9VV/V2.png"}
_BEEWATCH MK1 REV2_

### BEEWATCH MK1 Specifications

| **Feature**               | **Specification**                                                                 |
|---------------------------|-----------------------------------------------------------------------------------|
| **Display**               | 1.3-inch white OLED display                                                       |
| **RTC**                   | ISL1208                                                                          |
| **MCU**                   | ATMEGA328                                                                        |
| **Input**                 | 2-way navigational switch                                                        |
| **Sensors**               | Temperature sensor, Heartbeat sensor (optional)                                  |
| **Battery**               | 3.7V Li-Po 150mAh                                                                |
| **Dimension**             | 45x28x10mm                                                                       |
| **Weight**                | Approx 25g                                                                       |
| **Charging**              | Micro USB                                                                        |
| **Alarm/Buzzer**          | Yes                                                                              |


Now, many years later, I’m planning to create a new watch: **BEEWATCH MK2**. I’m not sure how many parts this project will have, but I’m excited to share my journey. Please enjoy my project notes!


## BEEWATCH MK2

This is completely different from MK1, like Iron Man suits 🤖. It will be very promising and capable hardware, opening up limitless possibilities. Here are the specs I'm planning to implement in MK2:

### BEEWATCH MK2 Bird's-eye Specifications

| **Feature**               | **Specification**                                                                 |
|---------------------------|-----------------------------------------------------------------------------------|
| **Display**               | 1.28-inch round TFT LCD display (RGB 240x240, GC9A01)                            |
| **RTC**                   | Internal RTC                                                                     |
| **Input**                 | 2 push buttons                                                                   |
| **MCU**                   | ESP32-S3                                                                         |
| **Sensors**               | Temperature sensor, 6-axis IMU (MPU6050)                                         |
| **Peripheral**            | GPS                                                                              |
| **Battery**               | 3.7V Li-Po 150mAh                                                                |
| **Dimension**             | ⌀40.2x10mm                                                                      |
| **Weight**                | Approx 25g                                                                       |
| **Charging**              | Type-C USB                                                                       |
| **Alarm/Buzzer**          | Yes                                                                              |

Here, we are using the **ESP32-S3**, which has Wi-Fi, Bluetooth, and GPS—a deadly combo! ☠️

Why? Because this hardware enables us to do a lot more than just tell time. Here are some possible applications:

## Possible Applications of BEEWATCH MK2

| **Category**               | **Applications**                                                                                   |
|----------------------------|---------------------------------------------------------------------------------------------------|
| **Fitness and Health**     | Step counting, calorie burn estimation, heart rate monitoring (with additional sensor), sleep tracking. |
| **Navigation**             | Real-time GPS tracking, route recording, location-based reminders.                                |
| **Sports and Adventure**   | Speed/distance tracking, altitude tracking, motion analysis for sports (e.g., golf, tennis).      |
| **Gesture Control**        | Detect gestures (e.g., flick wrist to change music), control smart home devices.                  |
| **Smart Notifications**    | Receive phone notifications (calls, messages), vibrate alerts, weather updates based on GPS.      |
| **Safety Features**        | Fall detection, emergency alerts with GPS coordinates.                                            |
| **Data Logging**           | Log motion (acceleration, gyroscope) and GPS data for analysis or research.                       |
| **Smart Home Integration** | Remote control for smart home devices, trigger actions based on location (e.g., turn on lights).  |
| **Time-Synced Features**   | Automatic time synchronization using GPS, time zone updates when traveling.                       |
| **Geofencing**             | Set virtual boundaries, get alerts when entering/leaving a specific area (e.g., parental control).|
| **Environmental Monitoring**| Add sensors (e.g., temperature, humidity) to monitor surroundings, log environmental data.       |
| **Wireless Communication** | Use Wi-Fi/Bluetooth to connect with other devices, act as a bridge between phone and IoT devices.|
| **Custom Watch Features**  | Custom watch faces with real-time data (steps, heart rate, weather), compass, stopwatch, timer.   |
| **Research and Development**| Test new algorithms (motion analysis, GPS tracking), prototype wearable applications.            |


Even with the ESP32, we can make a tiny hacking device ☠️. That’s why I call it **limitless possibilities**. However, I won’t implement all these features in the first revision. My first priority is to make a simple timekeeping watch with basic features. Later, I’ll work on the software to achieve some of the applications listed above.
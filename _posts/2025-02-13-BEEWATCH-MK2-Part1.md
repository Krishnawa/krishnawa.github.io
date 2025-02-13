---
title: BEEWATCH-MK2 Part 1
date: 2025-02-13 07:20:00 +530
categories: [Homelab, Project]
tags: [gps, watch, esp32]
comments: true
mermaid: true
math: true
image:
    path: https://i.postimg.cc/cLLjf5F8/BEEWATCH-MK3.jpg
    lqip: https://i.postimg.cc/cLLjf5F8/BEEWATCH-MK3.jpg
    alt: BEEWATCH MK2
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
| **Display**               | **1.3-inch white OLED display**                                                   |
| **RTC**                   | **ISL1208**                                                                       |
| **Sensors**               | **Temperature sensor, Heartbeat sensor (optional)**                               |
| **Battery**               | **3.7V Li-Po 150mAh**                                                             |
| **Dimension**             | **45x28x10mm**                                                                    |
| **Weight**                | **Aprox 25g**                                               |
| **Charging**              | **Micro USB**                                                     |
| **Alram/Buzzer**          | **Yes**                                                     |
| **Input**                 | **2 Way navigational switch**                                                     |





Now, many years later, I’m planning to create a new watch: **BEEWATCH MK2**. I’m not sure how many parts this project will have, but I’m excited to share my journey. Please enjoy my project notes!


## BEEWATCH MK2

This is completely different from MK1 like iron man suites🤖, so it will be  very promising and very capable hardware, by this hardware we  think limitless possibilities
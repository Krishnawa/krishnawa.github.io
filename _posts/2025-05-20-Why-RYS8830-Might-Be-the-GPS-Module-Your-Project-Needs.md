---
title: The One GPS Module Every DIYer Needs to Know About
date: 2025-05-20 07:40:00 +530
categories: [Homelab, Modules]
tags: [gps, gnss, urat,i2c]
comments: true
mermaid: true
math: true
image:
    path: https://i.postimg.cc/pTpkdDWv/RYS8830-3.png
    lqip: https://i.postimg.cc/pTpkdDWv/RYS8830-3.png
    alt: RYS8830
---

## Introduction

I'm working on a GNSS-based watch to get accurate time ⌚, so I needed a tiny GNSS module that's both affordable and easy to use. Luckily, I found the **RYS8830** from [Reyax](https://reyax.com), a Chinese company that designs and manufactures GNSS modules, along with LoRa, Bluetooth, and cellular (4G/LTE) modules for IoT (Internet of Things) applications.

The RYS8830 is available locally for me, which is a big plus. It's incredibly small, just **11 × 11 × 2.2 mm**  and has very low current consumption (idle current: **3.7 mA**, sleep current: **0.26 mA**), making it a perfect fit for my project. So I thought this module might be a good fit for your future project too.

### Key Features of the RYS8830 

- **Small SMD form factor (11 x 11 mm)**
- **Ultra low power consumption**
- **Enhanced GNSS filter and low noise amplifier (LNA)**
- **Embedded antenna** for simplified integration
- **Powered by SONY CXD5605AGF Engine**

These features make it ideal for compact, battery-powered projects like wearables and IoT sensors.

Personally, working with GNSS feels like dealing with alien technology 👽. Once you understand the magic behind it, it genuinely gives you goosebumps!

Just think about it: you're getting the **exact time from your GNSS receiver** by decoding the data from multiple GNSS satellites 🛰️ flying over **20,000 km++** above the Earth 🌍. Mind-blowing, right?

Maybe I'll write a blog about GNSS sometime in the future. Stay tuned!


## What This Blog Covers

In this blog, I'm introducing the tiny GPS module **RYS8830**, and with a development board  showing how we can communicate with it to gather useful information like:

- **Basic understanding of GNSS**
- **NMEA-0183 GNSS Message structure**
- **Time**
- **Date**
- **Position**
- **Speed**
- **Altitude**

Let’s explore how to bring precise satellite timing to your next DIY project!

## Basic Understanding of GNSS

If you think the GNSS module in your device (like your smartphone) gets location data by **sending a request to a satellite** and the satellite then **replies with your location**, you're actually mistaken.

Think about it — there are around **6.9 billion smartphones** in the world, plus many more GNSS-enabled devices in **vehicles, drones, aviation, maritime, farming**, and other applications totaling over **1.5 billion** additional devices. If each device were actively sending requests to satellites and waiting for a reply, imagine how many satellites and how much processing power that would require!

It's okay to think this way at first, but let's break down how it really works.

---

A **GNSS system** typically has **24 to 30+ satellites** orbiting Earth at around **20,000 km altitude**. These satellites are **constantly broadcasting radio signals** that include:
- Their current **position**
- The **exact time**, from highly precise **atomic clocks**

Your device like a smartphone or a GNSS module is a **passive receiver**. It **picks up these signals** from multiple satellites and **measures the time delay** between when the signal was sent and when it was received.

Using this delay, the receiver calculates the **distance** to each satellite. Then, it uses [**Trilateration**](https://en.wikipedia.org/wiki/Trilateration) to determine its exact position on Earth.

To calculate your position in 3D space (latitude, longitude, altitude), you need a **minimum of 3 satellites**. But there's a catch:  
Your device's clock is **not synchronized** with the atomic clocks in the satellites. Even a **microsecond** (1 µs) of timing error can cause a **300 km error** in calculated position.

To fix this, your receiver needs a **4th satellite** to solve for the **time offset**, so in practice, **you need at least 4 satellites** for an accurate location fix.

I'm not diving into too much detail here, but if you're curious, I recommend watching this [**YouTube video**](https://www.youtube.com/watch?v=qPTIi7Ds15M) for a better visual explanation.

---

You might notice that I often say “**GPS**” instead of “GNSS.” Why?

That’s because **GPS** was the **first GNSS**, built by the **United States**. It stands for **Global Positioning System**. It was initially developed for **military use**, and was opened to the public in the **1980s**, after a tragic incident in 1983 where a **civilian airliner (KAL 007)** was shot down due to navigation errors. Since then, GPS has become the **most widely used** term, even though today we have multiple GNSS systems like **GLONASS, Galileo, BeiDou,** and **NavIC**.

So, I use the word “GPS” simply because it’s more familiar and widely recognized, even though “GNSS” is the correct general term.

---

I hope this short overview helps you understand the **basic working of GNSS** and clears up common misconceptions!


Here are the different country GNSS system comparison table 
### 🛰️ Global GNSS Systems Comparison Table

| GNSS System | Country / Region | Constellation Name | # Satellites (Operational) | Frequency Bands      | Accuracy (Civil) | Altitude (km)             | Orbital Type       | Notes                                             |
|-------------|------------------|---------------------|-----------------------------|-----------------------|------------------|----------------------------|---------------------|---------------------------------------------------|
| **GPS**     | 🇺🇸 USA           | NAVSTAR              | 31+                         | L1, L2, L5            | ~5 m             | ~20,200                    | MEO                 | First GNSS, fully operational since 1995          |
| **GLONASS** | 🇷🇺 Russia        | GLONASS              | 23+                         | L1, L2, L3            | ~5–10 m          | ~19,100                    | MEO                 | Slightly lower orbits than GPS                   |
| **Galileo** | 🇪🇺 EU            | Galileo              | 28+ (24 usable)             | E1, E5, E6            | <1 m             | ~23,222                    | MEO                 | Dual-frequency for all users                     |
| **BeiDou**  | 🇨🇳 China         | BeiDou (BDS)         | 45+                         | B1, B2, B3            | ~2.5–5 m         | ~21,500 (MEO), ~36,000 (GEO) | MEO, IGSO, GEO     | BDS-3 offers worldwide coverage                  |
| **NavIC**   | 🇮🇳 India         | IRNSS / NavIC        | 7 (4 more planned)          | L5, S-band            | ~10–20 m         | ~36,000                    | GEO + IGSO         | Regional system covering India + 1500 km         |
| **QZSS**    | 🇯🇵 Japan         | QZSS (Michibiki)     | 4 (7 planned by 2025)       | L1, L2, L5, L6        | ~0.5–1 m (with GPS) | ~36,000                 | Quasi-Zenith + GEO | Regional GPS enhancement in Asia-Pacific region  |


## NMEA-0183 GNSS Message structure



fun fact
10.23MHz

The first consumer GPS receiver (1981, "Magellan NAV 1000") weighed 16 kg (35 lbs) and cost $100,000+! Today, a $10 chip in your phone does the same job.
 

![RYS8830 with a coin](https://i.postimg.cc/hPvfzjWm/RYS8830-Coin.png){: lqip="![https://i.postimg.cc/hPvfzjWm/RYS8830-Coin.png]" }

## Pin out 
![Pinout](https://i.postimg.cc/NfFPRBYv/RYS8830-PINOUT.png){: lqip="![https://i.postimg.cc/NfFPRBYv/RYS8830-PINOUT.png]" }

## Technical Specifications

### 🔌 Power Supply Voltage

| Item                                | Min. | Typical | Max. | Unit | Condition    |
| ----------------------------------- | ---- | ------- | ---- | ---- | ------------ |
| Power Supply Voltage (VDD)          | 1.71 | 1.8     | 1.89 | V    | VDD          |
| Power Supply Voltage (VDD\_LDO\_IN) | 0.9  | 1.8     | 1.95 | V    | VDD\_LDO\_IN |

### 🌐 GNSS Current consumption in different modes

| Item                          | Min. | Typical | Max. | Unit | Condition |
| ----------------------------- | ---- | ------- | ---- | ---- | --------- |
| Idle Current                  |      | 3.7     |      | mA   | (1)       |
| Satellite Acquisition Current | 16   | 19      |      | mA   | (1)(3)    |
| Satellite Tracking Current    | 9    | 13      |      | mA   | (1)(3)    |
| Idle Current                  |      | 3.3     |      | mA   | (2)(4)    |
| Satellite Acquisition Current |      | 11.5    |      | mA   | (2)(3)(4) |
| Satellite Tracking Current    |      | 8.2     |      | mA   | (2)(3)(4) |
| Sleep0 Mode Current           |      | 0.5     |      | mA   | (2)(4)    |
| Sleep1 Mode Current           |      | 0.26    |      | mA   | (2)(4)    |
| Sleep2 Mode Current           |      | 0.26    |      | mA   | (2)(4)    |
| Satellite Tracking Avg Current | 2.6  |         | 8.2  | mA   | (2)(3)(4) |




### 📡 Interface & Communication

| Item              | Value  | Unit | Notes           |
| ----------------- | ------ | ---- | --------------- |
| I2C Slave         | –      | –    | Clock: 400kHz   |
| Address Length    | 7 bits |      |                 |
| Slave Address     | 0x24   |      |                 |
| Default Baud Rate(UART) | 115200 | bps  | Format: 8, N, 1 |


### 💻 Digital Levels

| Item                    | Min     | Typical | Max     | Unit | Condition |
| ----------------------- | ------- | ------- | ------- | ---- | --------- |
| Input Level High (VIH)  | 0.7×VDD |         | VDD+0.3 | V    |           |
| Input Level Low (VIL)   | -0.3    |         | 0.3×VDD | V    |           |
| Output Level High (VOH) | 0.8×VDD |         | VDD     | V    | @2mA      |
| Output Level Low (VOL)  | 0       |         | 0.2×VDD | V    | @2mA      |


### 💾 Memory & RF

| Item                    | Value                          | Unit  | Notes                  |
| ----------------------- | ------------------------------ | ----- | ---------------------- |
| Flash Size              | 8                              | M-bit |                        |
| GNSS Center Frequencies | 1561.098 / 1575.42 / 1602.5625 | MHz   | BeiDou / GPS / GLONASS |

### 🛰️ GNSS Performance

| Item                   | Value | Unit | Condition                 |
| ---------------------- | ----- | ---- | ------------------------- |
| Navigation Update Rate | 1     | Hz   |                           |
| Accuracy               | 1     | M    | Signal strength: -130 dBm |
| Cold Start             | 35    | Sec. | Signal strength: -130 dBm |
| Hot Start              | 1     | Sec. |                           |
| Tracking Sensitivity   | -161  | dBm  |                           |
| Hot Start Sensitivity  | -160  | dBm  |                           |
| Cold Start Sensitivity | -147  | dBm  |                           |
| Altitude Limit         | –     | M    | No limit                  |
| Velocity Limit         | –     | 600  | M/s                       |


### 🌡️ Environment & Physical

| Item           | Min | Typical | Max | Unit | Notes               |
| -------------- | --- | ------- | --- | ---- | ------------------- |
| Operating Temp | -40 | 25      | +85 | ˚C   |                     |
| Dimensions     |     |         |     |      | 11mm × 11mm × 2.2mm |
| Weight         |     | 0.43    |     | g    |                     |


> (1) VDD_LDO_IN = 1.8V. (2) VDD_LDO_IN = 0.92V. (3) The typical value is field test. (4) Use buck regulator.
{: .prompt-info }


## Typical Applications

- IoT devices
- Wearables
- Asset tracking
- Drones and robotics


## What you need to get started

1. 1 x [RYS8830_EVB](https://www.amazon.com/REYAX-RYS8830_EVB-Glonass-Antenna-Interface/dp/B09BMZJMD9)
2. 1 x Micro USB Cable
3. 1 x Any Arduino compatible board (ESP32 Zero)
4. 1 x Bread board
5. Couple of wire
6. GNSS Software


### Getting Data from RYS8830_EVB to PC

1. Install the GNSS software
2. Connect the USB to RYS8830_EVB and PC
3.  Open the software GNSS_Monitor2_ForCustomer Target →RYS8830 select CXD5605
4. Open the Serial Port setting
5. Set the COM port number and the baud rate (Default is 115200bps).
6. If connection successful, will show FW version message.


Add screenshot 

results



### Getting Data from RYS8830_EVB to ESP32

connection steps

## Basic understanding of NEMA commands


## Arduino code and explanation

Arduino Lib

add screenshots 

results
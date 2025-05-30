---
title: Why RYS8830 Might Be the GPS Module Your Project Needs
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

I'm working on a GPS-based watch to get accurate time ⌚, so I needed a tiny GPS module that's both affordable and easy to use. Luckily, I found the **RYS8830** from [Reyax](https://reyax.com) — a Chinese company that designs and manufactures GNSS modules, along with LoRa, Bluetooth, and cellular (4G/LTE) modules for IoT (Internet of Things) applications.

The RYS8830 is available locally for me, which is a big plus. It's incredibly small — just **11 × 11 × 2.2 mm** — and has very low current consumption (idle current: **3.7 mA**, sleep current: **0.26 mA**), making it a perfect fit for my project. So I thought this module might be a good fit for your future project too.

### Key Features of the RYS8830 (Powered by SONY CXD5605AGF Engine)

- **Small SMD form factor (11 x 11 mm)**
- **Ultralow power consumption**
- **Enhanced GNSS filter and low noise amplifier (LNA)**
- **Embedded antenna** for simplified integration

These features make it ideal for compact, battery-powered projects like wearables and IoT sensors.

Personally, working with GPS feels like dealing with alien technology 👽. Once you understand the magic behind it, it genuinely gives you goosebumps!

Just think about it: you're getting the **exact time from your GPS receiver** by communicating with multiple GNSS satellites 🛰️ flying over **20,000 km** above the Earth 🌍. Mind-blowing, right?

Maybe I'll write a blog about GNSS sometime in the future. Stay tuned!


## What This Blog Covers

In this blog, I'm introducing the tiny GPS module **RYS8830**, and showing how we can communicate with it to gather useful information like:

- **Time**
- **Date**
- **Position**
- **Speed**
- **Altitude**

Let’s explore how to bring precise satellite timing to your next DIY project!

add a phto with coin

![RYS8830 with a coin](https://i.postimg.cc/hPvfzjWm/RYS8830-Coin.png){: lqip="![https://i.postimg.cc/hPvfzjWm/RYS8830-Coin.png]" }

## Pin out 
![RYS8830 with a coin](https://i.postimg.cc/3NmLQ1VL/IMG-20250527-214552-01.jpg){: lqip="!(https://i.postimg.cc/3NmLQ1VL/IMG-20250527-214552-01.jpg)" }
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


### 📦 Memory & RF

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
## Advantages Over Other Modules

- Lower power usage compared to competitors
- Faster cold and hot start times
- Better signal acquisition in challenging environments

## Typical Applications

- IoT devices
- Wearables
- Asset tracking
- Drones and robotics


## Communicating through UART to receive data from GPS constellation!


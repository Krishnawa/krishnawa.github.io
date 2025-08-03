---
title: EMI/EMC Testing with GTEM Cell for Pre Compliance
date: 2025-08-03 10:39:00 +530
categories: [Industry, Testing]
tags: [gtem,fcc,emi,emc]     # TAG names should always be lowercase
comments: true
mermaid: true
math: true
image:
  path: https://www.winmate.com/image/Technologyimg/Emc_img_01.jpg
  lqip: https://www.winmate.com/image/Technologyimg/Emc_img_01.jpg
  alt: GTEM 250 (Source:​​ https://www.ametek-cts.com)
---

## Why we are doing Electromagnetic Interference (EMI) and Electromagnetic Compatibility (EMC) testing?

Electromagnetic Interference (EMI) and Electromagnetic Compatibility (EMC) testing are done to make sure electronic devices, like phones or computers, work properly and don’t mess with other devices. 

- Stop Devices from Causing Trouble (EMI): EMI testing checks if a device gives off unwanted signals that could mess up things like radios, TVs, or medical equipment. The FCC (a U.S. regulator) has rules to keep these signals low so everything works smoothly.

- Make Sure Devices Can Handle Interference (EMC): EMC testing makes sure a device can still work when it’s around other signals, like from cell towers or power lines. It’s like checking if your phone still works near a strong Wi-Fi signal.

- Follow the Rules: The FCC requires these tests for devices sold in the U.S. If a device fails, it can’t be sold, and the maker could get in trouble.

- Keep Things Safe and Reliable: Testing prevents devices from failing in ways that could be dangerous (like in medical or car equipment) and ensures they work as promised.

- Get Products to Market: Passing these tests is like getting a “stamp of approval” to sell your device in the U.S.


## EMI/EMC Standards

Here are the most widely used families of standards:


### FCC (U.S.A)
#### Title 47 CFR Part 15 (Subparts B, C, E)
- Regulates EMI emissions for digital devices.
- Class A: Commercial/industrial equipment (less strict).
- Class B: Residential equipment (more strict).
- Radiated & conducted emissions are covered.
- Example: FCC Part 15 Subpart B (Unintentional Radiators).

### CISPR / IEC (International)
#### Developed by IEC and CISPR (International Special Committee on Radio Interference).
- CISPR 11: Industrial, scientific, medical (ISM) equipment.
- CISPR 22: Information technology equipment (similar to FCC Part 15).
- CISPR 32: Multimedia equipment (supersedes CISPR 22).
- CISPR 14: Household appliances.

### EN Standards (Europe)
#### EN standards are harmonized with the EU EMC Directive 2014/30/EU.

- EN 55032: Multimedia equipment emissions.
- EN 55024: Immunity requirements.
- EN 61000-4-x series: Immunity testing methods:
- EN 61000-4-2 (ESD immunity)
- EN 61000-4-3 (Radiated RF immunity)
- EN 61000-4-4 (EFT/Burst immunity)
- EN 61000-4-5 (Surge immunity)
- Products must have CE marking and Declaration of Conformity.

To test the EUT (Equipment Under Test) there are three popular methods
- Anechoic chamber
- GTEM cell
- Open area test

##  Anechoic chamber
![An RF anechoic chamber](https://upload.wikimedia.org/wikipedia/commons/0/0a/Radio-frequency-anechoic-chamber-HDR-0a.jpg){: lqip="https://upload.wikimedia.org/wikipedia/commons/0/0a/Radio-frequency-anechoic-chamber-HDR-0a.jpg" }
_An RF anechoic chamber (source: Wikipedia)_

An Anechoic Chamber is a shielded room lined with radio-frequency (RF) absorbing material on all sides, designed to simulate a free-space environment (like outer space, with no reflections).

#### Used For
- Radiated Emission Testing: Measure how much RF your product emits.
- Radiated Immunity Testing: Expose your product to controlled RF fields and see if it malfunctions.

#### Features
- Fully enclosed and shielded from external RF noise.
- RF absorbers prevent internal reflections (ensures accurate measurement).
- Controlled environment (temperature, humidity, no wind).

#### Pros
- Extremely accurate.
- Immune to external interference.
- Can test both large and small devices.
- Works across a wide frequency range (typically 30 MHz – 18 GHz or higher).

#### Cons
- Very expensive to build and maintain.
- Requires space and special infrastructure.
- Needs regular calibration and maintenance.

## GTEM Cell (Gigahertz Transverse Electromagnetic Cell)
![An RF anechoic chamber](https://ametekcdn.azureedge.net/mediafiles/ametekcts/importdata/images/highres/gtem/tem/sl/rc/gtem_250_r_en_1.png){: lqip="https://ametekcdn.azureedge.net/mediafiles/ametekcts/importdata/images/highres/gtem/tem/sl/rc/gtem_250_r_en_1.png" }
_GTEM 250 (Source:​​ https://www.ametek-cts.com)_

A GTEM Cell is a compact, tapered metal enclosure that creates a TEM (Transverse Electromagnetic) field, simulating a plane wave environment inside a shielded box.

#### Used For
- Radiated Emission (pre-compliance, R&D)
- Radiated Immunity testing (up to ~1 GHz or 2 GHz for advanced models)

#### Features
- Coaxial input feeds RF signal into the tapered chamber.
- EUT sits on an internal platform.
- Compact alternative to large chambers.

#### Pros
- Small footprint — fits on a lab table.
- Faster and cheaper than anechoic chamber.
- Shielded, so no external RF leaks.

#### Cons
- Field uniformity isn't perfect — less accurate than anechoic chambers.
- Limited size — only works for small DUTs (development boards, wearables, small devices).
- Limited frequency range (<2 GHz usually).

## Open Area Test Site (OATS)
![OATS](https://apctech.com/media/wysiwyg/Open-Area-Test-Site-_OATS_.png){: lqip="https://apctech.com/media/wysiwyg/Open-Area-Test-Site-_OATS_.png" }
_Open Area Test Site (OATS) (Source:​​ https://apctech.com)_
An Open Area Test Site is an outdoor testing environment with a large metal ground plane and no nearby reflecting structures. It's the traditional method for EMI radiated emission testing.

#### Used For
Radiated Emission Testing, mainly for formal compliance (e.g., FCC Part 15).

#### Features
- Outdoor setting.
- Standardized test distance (3m, 10m).
- Uses calibrated antennas and measurement equipment.

#### Pros
- Very accurate in ideal conditions.
- Official method accepted by regulatory bodies (FCC, CISPR).
- No chamber cost.

#### Cons
- Weather-dependent (rain, wind, temperature).
- Ambient RF noise can ruin measurements.
- Requires large open land and strict layout rules (vegetation, buildings, power lines must be far away).
- Time-consuming to set up.



### Summary: EMI/EMC Test Environments

| Environment        | Accuracy | Portability | Cost     | EUT Size         | Frequency Range   | Best For                          |
|-------------------|----------|-------------|----------|------------------|-------------------|-----------------------------------|
| **Anechoic Chamber** | ⭐⭐⭐⭐     | ❌          | 💰💰💰💰💰 | Medium to Large   | Up to 18 GHz+      | Final testing, certification labs |
| **GTEM Cell**        | ⭐⭐⭐      | ✅          | 💰💰💰     | Small             | Up to ~1–2 GHz     | Pre-compliance, R&D               |
| **Open Area Site**   | ⭐⭐⭐⭐     | ❌          | 💰💰       | Medium to Large   | 30 MHz – 1 GHz     | Formal radiated emission testing  |


## Radiated emission
![RE](/assets/img/EMI_EMC/RE.svg){: lqip="/assets/img/EMI_EMC/RE.svg" }
## Radiated immunity
![RI](/assets/img/EMI_EMC/RI.svg){: lqip="/assets/img/EMI_EMC/RI.svg" }
## Conducted emission
![CE](/assets/img/EMI_EMC/CE.svg){: lqip="/assets/img/EMI_EMC/CE.svg" }
## Conducted immunity
![CI](/assets/img/EMI_EMC/CI.svg){: lqip="/assets/img/EMI_EMC/CI.svg" }



### Reference
- https://www.tek.com/en/solutions/application/emi-emc-testing
- https://www.rohde-schwarz.com/us/solutions/electronics-testing/emc-testing/emc-testing_253441.html#gallery-14
- https://eepower.com/technical-articles/an-overview-of-conducted-emissions-part-1/#
- https://theemcshop.com/resources/
- https://www.intechopen.com/chapters/78512
- https://apctech.com/fully-anechoic-semi-anechoic-chambers-and-open-area-test-sites
- https://eepower.com/technical-articles/an-overview-of-conducted-emissions-part-1/
- https://www.emc-directory.com/community/what-is-immunity-testing-for-emc
- https://emcfastpass.com/emc-testing-beginners-guide/emc-immunity-testing/

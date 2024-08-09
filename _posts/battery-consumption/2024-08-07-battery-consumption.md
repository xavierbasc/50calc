---
layout: post
title: "Battery Consumption and Lifespan"
date: 2024-08-07 20:15:00 +01:00
categories: dm50 init battery lipo consumption lifespan
img1: /assets/img/LP305060.jpg
---

### DM50 System Power Consumption

Here's a breakdown of the power consumption for the main components of the DM50:

- **STM32U5 110MHz**: 1.7mA
- **LCD**: 320µA
- **REGULATOR**: 18μA
- **RAM standby**: 10µA

**TOTAL**: 2.0mA

### STM32 Microcontroller Power Consumption:

- **STM32U073CC**:  52μA/MHz run,  16nA off, 256KB FLASH,  40KB RAM
- **STM32L072CZ**:  93µA/MHz run, 860nA off, 192KB FLASH,  20KB RAM
- **STM32L151CC**: 185µA/MHz run, 440nA off, 256KB FLASH,  32KB RAM
- **STM32L451CE**:  84µA/MHz run,  22nA off, 512KB FLASH, 160KB RAM
- **STM32L4P5CG**:  41μA/MHz run,  22nA off,   1MB FLASH, 320KB RAM
- **STM32L552CE**:  62μA/MHz run,  17nA off, 512KB FLASH, 256KB RAM
- **STM32U535CE**:  16μA/MHz run,  90nA off, 512KB FLASH, 274KB RAM
- **STM32U575CI**:  20μA/MHz run, 160nA off,   2MB FLASH, 786KB RAM

As you can see, the STM32U5 stands out with its super-efficient active power consumption.

To make things even better, we’re working on some cool software tricks to minimize power usage, like auto shut-off, sleep mode, and reducing the MCU's clock speed to 110MHz.

### LiPO Batteries

Here are some LiPO battery options that could power up your calculator:

- **750mAh**: LP305048 3.0mm x 50mm x 48mm
- **800mAh**: LP304265 3.0mm x 42mm x 65mm
- **900mAh**: LP305060 3.0mm x 50mm x 60mm
- **900mAh**: LP305055 3.0mm x 50mm x 55mm

<figure>
<img src="{{ page.img1 }}" alt="LP305060">
<figcaption>LP305060 LiPO battery</figcaption>
</figure>

### Battery Life

Here's a rough idea of how long different batteries will last, based on an average of 8 hours of usage per day:

- **150mAh LiPO**: 75 hours (9 days)
- **900mAh LiPO**: 428 hours (53 days)
- **2000mAh (2xAAA)**: 952 hours (119 days)

So, with these estimates, you can pick the right battery to keep your calculator running as long as you need!

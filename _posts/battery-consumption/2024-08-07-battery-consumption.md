---
layout: post
title: "Battery Consumption and Lifespan"
date: 2024-08-07 20:15:00 +01:00
categories: dm50 init battery lipo consumption
img1: /assets/img/LP305060.jpg
img2: /assets/img/housing2.png
---

### DM50 System Power Consumption

Here's a breakdown of the power consumption for the main components of the DM50:

- **LCD**: 0.4mA
- **MCU STM32U5** at 160MHz: 2.5mA
- **MCU STM32U5** at 110MHz: 1.7mA
- **Total**: 2.1mA (at 110MHz)

### STM32 Microcontroller Power Consumption Comparison:

- **STM32U5**: 90 nA (shutdown) / 16 μA/MHz (active)
- **STM32U0**: 16 nA (shutdown) / 52 μA/MHz (active)
- **STM32L5**: 17 nA (shutdown) / 62 μA/MHz (active)
- **STM32L0**: 16 nA (shutdown) / 52 μA/MHz (active)

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

- **2000mAh (2xAAA)**: 952 hours (119 days)
- **900mAh LiPO**: 428 hours (53 days)
- **150mAh LiPO**: 75 hours (9 days)

So, with these estimates, you can pick the right battery to keep your calculator running as long as you need!
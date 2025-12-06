# CHICHI - The Slap-Reactive Smart Lamp

![CHICHI Overview](resources/chichi-overview.png)

CHICHI is a portable smart lamp shaped like a newly hatched chick in a cracked egg. It brings warm ambient light and playful personality wherever you go — responding to your touch with vibrant colors and breathing effects that make it feel alive.

## Why CHICHI?

In a world of cold screens and rigid devices, CHICHI brings warmth and emotion to your workspace or bedside. It's not just a lamp — it's a companion that responds to you, glows with you, and adds a touch of playfulness to your day. Whether you need focus lighting, a mood boost, or just something cute to brighten your desk, CHICHI is there.

## Features

- **Gesture-Controlled** - No buttons needed, just slap or tap
- **Adorable Design** - Shaped like a chick hatching from an egg
- **RGB LEDs** - WS2812B addressable LEDs for smooth animations
- **Portable & Rechargeable** - Built-in Li-Po battery with USB-C charging
- **Smart Interactions**:
  - **Single Slap** - Change colors
  - **Double Slap** - Power ON/OFF
  - **Idle Mode** - Soft breathing glow when untouched
- **Expandable** - ESP32-C3 with Wi-Fi & Bluetooth LE for future features
- **Compact & Cute** - Translucent 3D-printed shell with diffused lighting

## Schematic

![CHICHI Schematic](resources/chichi-schematic.png)

The circuit is built around the ESP32-C3 Supermini microcontroller with:
- 2x WS2812B addressable RGB LEDs in series (D5 → D6)
- Piezo disc sensor connected directly to ESP32 GPIO
- Battery Charger 1A module with USB input
- LiPo battery providing power to entire system
- Simple, compact design with minimal external components

## PCB Design

![CHICHI PCB](resources/chichi-pcb.png)
![CHICHI PCB](resources/chichi-3d-pcb.png)
Custom PCB designed for compact integration inside the egg shell:
- 2 WS2812B LEDs (D5 and D6) for efficient lighting
- ESP32-C3 Supermini module headers
- Battery Charger 1A module integration
- Piezo sensor connection pads
- LiPo battery connector

## Case Design

![CHICHI Case Assembly](resources/chichi-3d.png)

The 3D-printed case features:
- Translucent white PLA/PETG for frosted glow effect
- Two-piece egg design (cracked shell aesthetic)
- Internal cavity for PCB and battery
- Smooth surface finish for even light diffusion
- Compact size: 60-90mm tall (customizable)
- added a cyylinder to be able to open case easily.

Here's your updated BOM with prices and links:

## Bill of Materials (BOM)

| Component | Quantity | Price (INR) | Price (USD) | Link | Notes |
|-----------|----------|-------------|-------------|------|-------|
| ESP32-C3 Supermini | 1 | ₹400 | $4.76 | [Quartz Components](https://quartzcomponents.com/products/esp32-c3-super-mini-development-board-with-soldered-headers-hw-466ab?variant=45727228887274) | Microcontroller (with shipping) |
| WS2812B RGB LED | 2 | ₹360 | $4.29 | [Amazon India](https://www.amazon.in/gp/product/B09PBCQTNR/ref=ewc_pr_img_6?smid=A2JDRZEGU1IDE2&psc=1) | Addressable LEDs (D5, D6) |
| Piezo Disc Sensor | 1 | ₹100 | $1.19 | [Amazon India](https://www.amazon.in/gp/product/B0CZLLN13J/ref=ox_sc_act_title_1?smid=A1UUD7CBBVVXIG&psc=1) | 27-35mm diameter |
| TP4056 Type-C Charging Module | 1 | ₹162 | $1.93 | [Flipkart](https://www.flipkart.com/robo-ocean-charging-module-tp4056-type-c-pack-5-1a-li-ion-current-protection-electronic-components-hobby-kit/p/itm6bd0ee4c5a1a8?pid=EHKH97UJFKPKW5HZ&lid=LSTEHKH97UJFKPKW5HZFH99NA&marketplace=FLIPKART) | 1A USB charging circuit (with shipping) |
| Li-Po Battery 603443 | 1 | ₹299 | $3.56 | [Amazon India](https://www.amazon.in/gp/product/B0D54MCMKC/ref=ewc_pr_img_3?smid=A3QQB9C2QXM7ZJ&psc=1) | 3.7V, 800mAh, 2.96Wh |
| MT3608 Boost Converter | 1 | ₹100 | $1.19 | [Amazon India](https://www.amazon.in/Adjustable-converter-Regulator-Transformer-Controller/dp/B08LTLV74H/) | DC-DC step-up for stable 5V output |
| Custom PCB | 1 | ₹840 | $10.00 | - | Main circuit board |
| 3D Printed Shell | 1 set | ₹420 | $5.00 | - | Top + Bottom egg pieces |


---

### **Total Estimated Cost:**
- **₹2,731 - ₹2,781** (INR)
- **$32.52 - $33.11** (USD)

**Note:** Currency conversion based on approximate rate of ₹84 = $1 USD
BOM csv: [here!](https://github.com/jai-git4208/chichi/blob/main/resources/bom.csv)

## Interaction Modes

### Single Slap - Color Change(need to add btw)
A gentle slap on the shell cycles through vibrant color modes:
- **Warm White** - Cozy ambient lighting
- **Cool White** - Focus and productivity
- **Red Glow** - Evening/night mode
- **Blue Wave** - Calm and serene
- **Green Pulse** - Nature vibes
- **Purple Dream** - Creative energy
- **Rainbow Fade** - Playful and dynamic
- **Breathing Mode** - Slow pulsing (any color)

### Double Slap - Power Toggle
Two quick slaps turn CHICHI on or off. The LEDs fade smoothly to preserve battery and provide satisfying feedback.

### Idle Mode - Breathing Glow
When left alone, CHICHI breathes with a soft, warm glow — making it feel alive even when you're not interacting with it. Perfect for ambient mood lighting.

## Technical Specifications

### Power System
- **Battery**: 3.7V Li-Po (500-1200 mAh)
- **Charging**: Battery Charger 1A module via USB (5V input)
- **Runtime**: 3-6 hours depending on brightness
- **Power Distribution**: Direct battery power to ESP32 and LEDs
- **Deep Sleep**: Ultra-low power consumption when idle

### Microcontroller
- **Model**: ESP32-C3 Supermini
- **Core**: RISC-V single-core (32-bit)
- **Features**: Wi-Fi 802.11b/g/n, Bluetooth LE 5.0
- **Programming**: Arduino IDE / CircuitPython support
- **GPIO**: Digital I/O for LEDs and piezo sensor
- **Power**: 3.3V operation with onboard regulation

### Lighting Engine
- **LEDs**: 2x WS2812B addressable RGB (D5, D6)
- **Arrangement**: Series connection for synchronized lighting
- **Control**: Single data line from ESP32 GPIO
- **Voltage**: 5V LEDs powered by battery
- **Effects**: Solid colors, transitions, breathing, animations
- **Brightness**: Software-controlled PWM

### Sensor System
- **Type**: Piezo disc vibration sensor (piezo2)
- **Size**: 27-35mm diameter
- **Connection**: Direct to ESP32 GPIO
- **Detection**: Tap, slap, and pressure events
- **Signal Processing**: Software debouncing and threshold detection



## Design Files

- **PCB**: KiCad project files in `PCB/` folder
- **Case**: STEP and STL files in `CAD/` folder  
- **Firmware**: Arduino code in `Firmware/` folder
- **Resources**: Schematics and images in `resources/` folder


## Preferences

- **Shell Color**: Translucent White (frosted)
- **LED Ring**: Warm white base with RGB accents
- **Charging Port**: USB-C (accessible from bottom)

## Credits

Designed and built for the Hack Club Blueprint program.

**Designer**: JAIMIN PANSAL  
**GitHub**: [jai-git4208](https://github.com/jai-git4208)  
**License**: MIT

---

## With ❤️ by Jaimin

*"CHICHI isn't just a lamp — it's a little friend that glows with you."*

#  Audio Receiver

This marks the beginning of my journey towards building a small audio receiver **from scratch**.

---

##  Overview

The receiver uses two **TDA2030A** amplifier chips, each driving its own respective channel (stereo amplification, one chip per channel).

Control and input switching are handled by an **ESP32**, which brings a few nice options to the table:

- **Bluetooth audio** — using the ESP32's built-in Bluetooth capabilities paired with its two built-in DAC pins (`GPIO 25` and `GPIO 26`)
- **High-quality digital audio** — via an I2S bus, using a PCM5102A DAC.

##  Input Selector

The input selector is built around:

- An **SSD1306 128x64 OLED display** (I2C)
- A handful of **buttons**
- A **KY-040 rotary encoder**

Together, these let you cycle through the menu, switch between inputs, and navigate settings.

---

##  Hardware Summary

| Component | Purpose |
|---|---|
| 2× TDA2030A | Stereo amplification, one channel each |
| ESP32 | Control, input switching, Bluetooth & I2S audio |
| SSD1306 OLED (128x64) | Menu / input display (I2C) |
| KY-040 Rotary Encoder | Menu navigation |
| Buttons | Additional input controls |

---

##  Progress Log

### v0.1 — Amplifier POC (July 22nd)

The first proof-of-concept amplifier board has been designed. As a POC, it keeps things simple:

- Regular conductive points for power
- Speaker terminals
- A 2200µF filtering capacitor

 **Schematic:** Images/schematics/v0.1
 **3D Render:** Images/renders/v0.1

> Fun detail: the board's front silkscreen features a **harp seal pup** because seals are my favorite animals 
### v1.0 — Stereo Amplifier board (July 23rd)

The first revision of the official amplifier PCB has been designed. It now features:

- A dual gang A47K potentiometer for volume controls. The reason an A47K was used instead of a B47K is because A47K (audio/logarithmic) potentiometer is better by matching the logarithmic way human hearing perceives loudness, giving a smooth and natural volume adjustment instead of most of the volume change happening near one end of the knob.
- A PCM5102A digital to analog converter for converting the ESP32's digital signals received from Bluetooth to analog signals which can be fed into the amplifier.
Once again, images of the new edition have been provided in Images/amplifier/V1.0
### v0.1 — Controller  (August 5th)

Once the amplifier board has been completed; it was time to make it smart. Hence the controller board.
The current work-in-progress controller features an ESP32 board for Bluetooth and audio switching. To get a better 3D footprint and to ease the schematic for viewing, I have used syauqibilfaqih's symbol and footprint (https://github.com/syauqibilfaqih/ESP32-DevKit-V1-DOIT).

### v1.0 — Controller  (August 21st)
The Controller Board serves as the user-interface and digital-audio control section of the amplifier system. It is built around an ESP32-DevKit-V1, providing Bluetooth audio, system control, and communication with the amplifier board. A PCM5102A DAC converts the ESP32's I²S digital audio into an analog stereo signal for the amplifier stage. The board includes an SSD1306 OLED display connected through I²C for displaying system information and settings. A KY-040 rotary encoder provides menu navigation, volume adjustment, and user input. Dedicated connectors expose the ESP32's I²S, I²C, power, and ground connections where required. The controller communicates with the amplifier board through the audio and control connections, allowing both boards to operate as a single integrated system. Local decoupling capacitors are provided around the ESP32, DAC, and display circuitry for stable operation. The board operates primarily from 3.3 V logic and is designed to work alongside the main amplifier board.

---

##  Status

 Work in progress — more updates to come as the project develops.

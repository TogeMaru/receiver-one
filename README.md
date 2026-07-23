# 🎧 DIY Audio Receiver

This marks the beginning of my journey towards building a small audio receiver **from scratch**.

---

## 🔊 Overview

The receiver uses two **TDA2030A** amplifier chips, each driving its own respective channel (stereo amplification, one chip per channel).

Control and input switching are handled by an **ESP32**, which brings a few nice options to the table:

- **Bluetooth audio** — using the ESP32's built-in Bluetooth paired with its two built-in DAC pins (`GPIO 25` and `GPIO 26`)
- **High-quality digital audio** — via an I2S bus, with dedicated pins for Data, Clock, and Word Select

## 🎛️ Input Selector

The input selector is built around:

- An **SSD1306 128x64 OLED display** (I2C)
- A handful of **buttons**
- A **KY-040 rotary encoder**

Together, these let you cycle through the menu, switch between inputs, and navigate settings.

---

## 🛠️ Hardware Summary

| Component | Purpose |
|---|---|
| 2× TDA2030A | Stereo amplification, one channel each |
| ESP32 | Control, input switching, Bluetooth & I2S audio |
| SSD1306 OLED (128x64) | Menu / input display (I2C) |
| KY-040 Rotary Encoder | Menu navigation |
| Buttons | Additional input controls |

---

## 📅 Progress Log

### v0.1 — Amplifier POC (July 23rd)

The first proof-of-concept amplifier board has been designed. As a POC, it keeps things simple:

- Regular conductive points for power
- Speaker terminals
- A 2200µF filtering capacitor

📄 **Schematic:** [`images/schematics/v0.1`](images/schematics/v0.1)
🖼️ **3D Render:** [`images/renders/v0.1`](images/renders/v0.1)

> Fun detail: the board's front silkscreen features a **harp seal pup** — seals are my favorite animals 🦭

---

## 📌 Status

🚧 Work in progress — more updates to come as the project develops.

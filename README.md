# AS7343 18-Channel Spectral Sensor with Gain Control

Real-time spectral analysis system with calibrated measurements for light characterization and grow light analysis.

![1_image1](https://github.com/benb0jangles/AS7343-18-Channel-Spectral-Sensor-with-Gain-Control/blob/main/img/Screenshot%202026-01-16%20at%2012.02.40%20Medium.jpeg)


## Overview

This project provides complete firmware and GUI software for the **AMS AS7343** 18-channel spectral sensor, enabling professional-grade light measurements including Lux, PAR, PPFD, CCT, and spectral power distribution visualization.

## Hardware

- **Sensor:** AMS AS7343 14-channel spectral sensor (18-channel mode)
- **Microcontroller:** ESP32-C3
- **Communication:** USB Serial (115200 baud)
- **Power:** USB-C

## Features

### Basic GUI
- Real-time spectral data visualization (18 channels: 405nm-910nm)
- Time-series graphs and bar charts
- Adjustable gain (0.5x to 2048x)
- LED control for reflectance/ambient measurements
- Channel filtering and auto-scaling
- PWM flicker detection

### Advanced GUI
- **Calibrated measurements:** Lux, Foot-Candles, CCT, Blue%, PAR, PPFD
- **Runtime calibration** with user's reference meters
- **Lux-to-PPFD estimation** (no quantum sensor required)
- **SPD visualization** with McCree curve overlay
- **Per-gain calibration** with persistent storage
- Spectrum-specific conversion for different light sources

## Quick Start

### 1. Upload Firmware
```bash
# Open as7343_18ch_gain_esp32c3/as7343_18ch_gain_esp32c3.ino in Arduino IDE
# Select: Board: ESP32C3 Dev Module
# Upload to ESP32-C3
```

### 2. Install Python Dependencies
```bash
pip install pyserial matplotlib numpy
```

### 3. Run GUI
```bash
# Basic GUI (real-time monitoring)
python as7343_18ch_gain_gui.py

# Advanced GUI (calibrated measurements)
python as7343_advanced_gui.py
```

## Use Cases

- **Horticulture:** Measure grow light PPFD and optimize spectrum for plants
- **Lighting Design:** Characterize Lux, CCT, and CRI of light sources
- **Quality Control:** Compare LED products against specifications
- **Research:** Analyze spectral characteristics of materials and light sources
- **Photography:** Evaluate light quality for color accuracy
- **Flicker Detection:** Identify PWM dimming in LED lights

## Calibration

Calibrate with your own reference equipment:
- **Lux calibration:** Any lux meter or smartphone lux app
- **PAR calibration:** Quantum sensor (optional - can estimate from Lux)

Calibrations are stored per gain setting and persist across sessions.

## Measurements

### Supported Metrics
- **Lux / Foot-Candles** - Illuminance
- **CCT** - Correlated Color Temperature (K)
- **Blue %** - Blue light percentage
- **PAR** - Photosynthetically Active Radiation
- **PPFD** - Photosynthetic Photon Flux Density (μmol/m²/s)
- **SPD** - Spectral Power Distribution

### 18 Spectral Channels
```
F1-F8:    405nm, 425nm, 450nm, 475nm, 515nm, 550nm, 555nm, 600nm
Clear:    Broadband visible light
NIR:      910nm near-infrared
F5L-F8L:  Duplicate channels (left photodiode)
FD/FDL:   Flicker detection
```

## Requirements

### Hardware
- AS7343 sensor breakout board (SparkFun, Adafruit, or equivalent)
- ESP32-C3 development board
- USB-C cable

### Software
- Arduino IDE with ESP32 board support
- Python 3.7+

### Optional (for calibration)
- Lux meter or smartphone with lux app
- Quantum sensor (for direct PAR calibration)

## License

MIT License 

## Author

benb0jangles 2026

## Acknowledgments

- AMS AG for AS7343 sensor
- SparkFun Electronics for AS7343 Arduino library
- Samsung Electronics for LM301H grow light datasheet reference

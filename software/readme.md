# 💧 POC Urine Dipstick Analyzer


This repository contains the **hardware firmware** and **Python GUI** for a **portable point-of-care urinalysis device**. The system provides continuous, on-demand analysis of urine using **dipstick-based colorimetric sensing** and delivers real-time insights through a connected mobile interface.

---

## 🧠 System Overview

The POC device is built around two core modules:

1. 🧾 **On-Demand Dipstick Dispenser**  
2. 🧪 **Automated Colorimetric Analyzer**

The user pulls a dipstick (like a ticket), dips it into a urine sample, and reinserts it into the device. The system captures RGB color data, processes it, and transmits results via Bluetooth or serial connection.

---

## ⚙️ Electronics & Components

| Component                  | Description                       |
|---------------------------|-----------------------------------|
| ESP32                     | Microcontroller (Espressif)       |
| TCS34725                  | RGB color sensor (AMS)            |
| 6V 100 RPM DC Motors × 2  | For dispensing and actuation      |
| MX1508 Motor Driver       | Dual H-bridge for motor control   |
| IR Emitter/Receiver       | Dipstick position detection       |
| Tkinter + PySerial        | GUI and communication framework   |

---

## 📁 Repository Structure

### `firmware.ino`
- **Platform:** Arduino (ESP32)
- **Functions:**
  - Controls motors and sensors
  - Reads color from TCS34725
  - Listens to serial commands from GUI
  - Sends RGB readings to host

### `gui.py`
- **Platform:** Python 3.x
- **Dependencies:** `pyserial`, `matplotlib`, `tkinter`
- **Functions:**
  - Connects to the ESP32 via serial
  - Sends commands for dispensing and scanning
  - Plots and stores RGB sensor data in real-time

---

## 🖥️ How to Run

### 1. Flash Firmware
Upload `firmware.ino` to an ESP32 board using Arduino IDE or PlatformIO.

### 2. Launch GUI

Install dependencies:

```bash
pip install pyserial matplotlib

### 3. Run the GUI:
```bash
python gui.py


Connect your ESP32 via USB and choose the correct serial port from the interface.

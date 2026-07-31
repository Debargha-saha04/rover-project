# DIY ESP32-S3 Gaming Controller

A custom dual-microcontroller gaming controller built using an ESP32 DevKit and an ESP32-S3. The project is designed as a fully functional wired gaming controller for PC gaming while also serving as the foundation for a portable retro gaming console.

---

# Basic Idea / Plan / Motive

The objective of this project is to design and build a gaming controller completely from scratch using ESP32 microcontrollers. The controller is intended to function as a USB gamepad for PC gaming while also supporting retro game emulation through Retro-Go in future versions.

The project focuses on modular firmware, hardware abstraction, and expandability, making it easy to integrate additional features such as SD card support, audio, battery management, and custom firmware.

---

# Basic Working

- Read joystick, trigger and button inputs using an ESP32 DevKit.
- Process and normalize all controller inputs.
- Transmit processed controller data to the ESP32-S3 through UART.
- Display controller status and menus on the TFT display.
- Present the device as a USB HID controller to a connected PC.

---

# Basic Architecture

```text
                      ┌───────────────────────┐
                      │      PC / Laptop      │
                      │   USB HID Interface   │
                      └───────────┬───────────┘
                                  │ USB
                                  │
                      ┌───────────▼───────────┐
                      │       ESP32-S3        │
                      │                       │
                      │ • USB HID            │
                      │ • TFT Display        │
                      │ • SD Card Interface  │
                      │ • System Menu        │
                      │ • Retro-Go (Planned) │
                      └───────────┬───────────┘
                                  │ UART
                                  │
                      ┌───────────▼───────────┐
                      │     ESP32 DevKit      │
                      │                       │
                      │ • Input Processing    │
                      │ • Joystick Reading    │
                      │ • Button Reading      │
                      │ • Trigger Reading     │
                      │ • MPU6050 Processing  │
                      └───────┬───────┬───────┘
                              │       │
              ┌───────────────┘       └────────────────┐
              │                                        │
      Analog Joysticks                     Buttons, D-Pad,
                                            Triggers & MPU6050
```

---

# Hardware

## Input Controller

- ESP32 DevKit
- Dual Analog Joysticks
- Hall Effect Triggers
- D-Pad
- Action Buttons
- MPU6050 Motion Sensor

## Main Controller

- ESP32-S3
- 320×240 TFT LCD Display
- USB Type-C
- SD Card Module
- Speaker (Planned)
- mic(planned)
---

# Software

- Arduino Framework
- FreeRTOS
- TFT_eSPI
- USB HID
- UART Communication


---

# Current Capabilities

- Analog joystick input
- Trigger input
- Multiple button inputs
- MPU6050 integration
- UART communication between controllers
- TFT display interface
- Wired USB communication
- SD card read/write support
- Modular firmware structure

---

# Planned Features

- XInput compatible controller
- Retro-Go integration
- SD card ROM loading
- Audio output
- Multiple controller profiles
- Battery support
- Custom boot animation
- Settings menu
- Diagnostic interface
- Controller calibration
- Save settings to SD card

---

# Controller Interface

The controller uses dual analog joysticks, Hall Effect triggers, a D-Pad and multiple push buttons for user input. An ESP32 DevKit processes all controller inputs before sending the processed data to the ESP32-S3 over UART.

The ESP32-S3 manages the TFT display, USB communication, SD card interface and future retro gaming features.

---

# Future Scope

Future versions of the project aim to transform the controller into a complete handheld gaming platform by integrating Retro-Go, SD card ROM management, audio playback, battery operation, and additional customization features while maintaining a modular software architecture.

---

This project is currently under active development, with additional hardware support and software features planned for future revisions.


<img width="1440" height="1920" alt="image-1783072790698" src="https://github.com/user-attachments/assets/405496da-2793-42f4-92d8-9a357419c5f4" />

<img width="4624" height="3472" alt="IMG_20260627_153823" src="https://github.com/user-attachments/assets/8d40d2c6-ec96-4fbf-b947-5e62112b2a72" />

<img width="4624" height="3472" alt="IMG_20260721_094601" src="https://github.com/user-attachments/assets/b900a4c3-058c-4cc5-88b8-9d35e5cc1539" />





https://github.com/user-attachments/assets/9a7ff0f0-6a62-4db4-8fcb-59563ac97f79



https://github.com/user-attachments/assets/c2fa1dc4-550c-401e-8df6-b6b7b4b63e88



<img width="4624" height="3472" alt="IMG_20260627_153823" src="https://github.com/user-attachments/assets/ae9cdf0d-95a3-41a8-a556-57c64b32d8aa" />
<img width="1599" height="899" alt="IMG-20260731-WA0017" src="https://github.com/user-attachments/assets/ce07377e-6209-400c-8a60-b3a3dac3ac17" />


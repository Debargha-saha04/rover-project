# Smart FPV Rover

A modular Wi-Fi controlled FPV rover developed using an **ESP32-CAM**, **Raspberry Pi Pico 2 W**, and **Arduino Nano**.

The project separates sensing, control, and networking across multiple microcontrollers to improve modularity, reliability, and future scalability. The rover supports wireless driving, live telemetry, obstacle sensing, and is designed as a foundation for future autonomous navigation.

---

# Architecture

```text
          Phone / Laptop
                 │
           Wi-Fi (HTTP)
                 │
                 ▼
            ESP32-CAM
    (Web Server • FPV • UI)
                 │ UART
                 ▼
          Raspberry Pi Pico 2 W
 (Motor Control • Sensor Fusion • Logic)
         │                │
         │ UART           │ I²C
         ▼                ▼
   Arduino Nano     MPU6050 + QMC5883
 (VL53L1X Node)          │
         │               │
         └───────────────┤
                         ▼
                Ultrasonic Sensor
                         │
                         ▼
                 Motor Driver & Motors
```

---

# Features

- Wi-Fi based wireless control
- ESP32-CAM web dashboard
- Multi-microcontroller architecture
- Live telemetry transmission
- Real-time obstacle detection
- Ultrasonic rear sensing
- VL53L1X Time-of-Flight front sensing
- MPU6050 IMU
- Digital compass navigation
- Servo-controlled camera mount
- Modular firmware design

---

# Hardware

- ESP32-CAM
- Raspberry Pi Pico 2 W
- Arduino Nano
- VL53L1X ToF Sensor
- HC-SR04 Ultrasonic Sensor
- MPU6050 IMU
- QMC5883 Digital Compass
- L298N Motor Driver
- Dual DC Gear Motors
- Pan-Tilt Servo Mechanism
- Li-ion Battery Pack

---

# Software

- MicroPython
- Arduino Framework
- HTTP Web Server
- UART Communication
- I²C Communication
- PWM Motor Control
- Sensor Fusion
- Wi-Fi Networking

---

# System Architecture

The rover follows a distributed embedded architecture where each controller performs a dedicated task.

### ESP32-CAM

- Hosts the Wi-Fi web interface
- Receives control commands
- Streams telemetry
- Supports FPV camera integration
- Communicates with the Pico over UART

### Raspberry Pi Pico 2 W

- Main rover controller
- Motor control
- Servo control
- Sensor fusion
- Telemetry generation
- Command processing

### Arduino Nano

- Dedicated VL53L1X sensor node
- Time-of-Flight distance measurement
- UART communication with Pico

---

# Telemetry

The rover continuously generates telemetry including:

- Heading
- Ultrasonic distance
- VL53L1X distance
- Accelerometer data
- Gyroscope data
- IMU temperature

Example:

```text
HEAD:56.8
US:29.4
VL:580
AX:-0.02
AY:0.03
AZ:0.82
GX:0.96
GY:0.44
GZ:-0.44
TEMP:32.3
```

---

# Current Status

### Completed

- Multi-controller communication
- Wi-Fi dashboard
- Wireless command system
- Telemetry pipeline
- Motor control
- Servo control
- VL53L1X integration
- MPU6050 integration
- QMC5883 integration
- Ultrasonic sensing

### In Progress

- FPV live camera streaming
- Compass calibration
- Navigation refinement

### Planned Features

- Autonomous obstacle avoidance
- Path planning
- Waypoint navigation
- SLAM experiments
- Object detection using ESP32-CAM
- Mobile-friendly dashboard
- OTA firmware updates

---

# Future Scope

The project serves as a foundation for an autonomous mobile robotics platform capable of combining wireless teleoperation with onboard sensing and future computer vision capabilities.

<img width="2160" height="3840" alt="IMG-20260627-WA0005" src="https://github.com/user-attachments/assets/c10bd357-e734-4c93-bb76-e9d47823c639" />
<img width="1599" height="899" alt="WhatsApp Image 2026-07-31 at 10 50 34 PM" src="https://github.com/user-attachments/assets/8dd2a164-cfc6-49dd-9edc-e8405ffd6f27" />
<img width="1599" height="899" alt="WhatsApp Image 2026-07-31 at 10 50 13 PM" src="https://github.com/user-attachments/assets/a647c82a-3729-4f89-a80c-501dafedc636" />
<img width="1599" height="899" alt="WhatsApp Image 2026-07-31 at 10 49 55 PM" src="https://github.com/user-attachments/assets/4fec050c-6500-4672-a732-cd4d46bb01bc" />
<img width="1599" height="899" alt="WhatsApp Image 2026-07-31 at 10 49 48 PM" src="https://github.com/user-attachments/assets/381415ce-0170-4fac-a1c4-e354d4c8318e" />
<img width="1599" height="899" alt="WhatsApp Image 2026-07-31 at 10 49 20 PM" src="https://github.com/user-attachments/assets/73c52d60-62e3-4e5c-b321-0961446c5bc6" />


https://github.com/user-attachments/assets/4964a8ad-545d-4fbd-96b6-b49fc1baac9a



https://github.com/user-attachments/assets/dc02c913-72af-4557-a315-713d0b06a7d7



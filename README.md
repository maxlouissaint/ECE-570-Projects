# ESP32 IMU Telemetry System

> Originally developed as **ECE 570 – Project 1** for the Computer Network course.

Embedded telemetry system that acquires motion data from an MPU6050 IMU over I2C, processes the sensor data on an ESP32, and transmits telemetry over Wi-Fi using UDP to a Python-based visualization server.

## Overview

The system uses an ESP32 to interface with an MPU6050 inertial measurement unit over I2C. The MPU6050 provides:

- 3-axis acceleration
- 3-axis angular velocity
- Temperature data

The ESP32 processes the acceleration measurements to calculate pitch and roll angles, then transmits the resulting telemetry over Wi-Fi using UDP.

A Python-based server running on a local computer receives and interprets the UDP packets and provides real-time visualization. A 3D cube rotates according to the calculated pitch and roll angles to represent the sensor's physical orientation.

## System Architecture

```text
MPU6050 IMU
    │
    │ I2C
    ▼
ESP32
    │
    │ Wi-Fi / UDP
    ▼
Python UDP Server
    │
    ▼
Real-Time 3D Visualization
```

## Documentation

Detailed implementation diagrams, hardware connections, debugging analysis, and project results are available in:

[`docs/Project 1 Report.pdf`](docs/Project%201%20Report.pdf)

The report includes:
- ESP32-to-MPU6050 pin connection diagram
- ESP32/MPU6050 firmware control-flow diagram
- Python UDP server and visualization control-flow diagram
# AirCom - The airbrake module 🚀

## Overview
This PCB is designed for active airbrake control in high-powered rockets, enabling real-time aerodynamic drag adjustments for precise apogee targeting. The system integrates multiple sensors, servo drivers, and comprehensive data logging capabilities.

## Core Features 📌

### Microcontroller & Processing
- STM32G431RBTx (Cortex-M4 with FPU, 170MHz)
- Timer Configuration:
  - TIM2, TIM4, TIM16, TIM17 for servo PWM control
  - Multiple communication interfaces (SPI, I²C, UART)
- Dual Operation Modes:
  - Flight Mode: Autonomous airbrake control
  - USB Configuration Mode: Apogee setup & telemetry access

### Sensor Suite 🔧
- IMU: BMI088 (SPI) - 6-DOF accelerometer & gyroscope
- Altimeter: MS5607 (SPI) - High-precision barometric sensing
- Magnetometer: MMC5983MA (I²C) - Orientation tracking
- Temperature: TMP275 (I²C) - System thermal monitoring

### Control Systems ⚙️
- 4x Servo Motor Outputs (PWM)
  - Independent flap control for roll, yaw, pitch, and drag
  - 3.3V to 5V level shifting via SN74HCT125DR
- Level Shifting Implementation:
  - SN74HCT125DR buffer
  - 2N7002 MOSFETs

### Data Management 💾
- Storage: W25Q256 NOR Flash (256Mbit)
  - 500Hz flight data logging
  - Complete telemetry storage
- USB-C Interface (C169130)
  - Virtual COM Port for configuration
  - Real-time telemetry access

### Power Architecture ⚡
- Dual Power Sources:
  - Battery: 3-17V input (TPS62153 buck converter to 5V)
  - USB-C: 5V VBUS
- Automatic Source Selection: NRVB120VLSFT1G Schottky diodes
- Voltage Regulation:
  - TPS62153: 5V, 1A buck regulator for servos
  - LP5912: 3.3V LDO for core systems

### Protection Features 🛡️
- Reverse Battery Protection
- USB ESD Protection (USBLC6-2SC6)
- Optimized Component Layout:
  - Strategic decoupling capacitor placement
  - Minimal SPI/I²C trace lengths

## Performance Specifications ✨
- 500Hz data sampling and logging
- Reliable servo control system
- Seamless power source switching
- Ruggedized design for high-G environments

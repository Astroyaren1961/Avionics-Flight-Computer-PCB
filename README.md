# Rocket Avionics Flight Computer PCB (STM32F407)

A custom 2-layer prototype Printed Circuit Board (PCB) designed in **KiCad** for competitive rocketry avionics and telemetry applications (TEKNOFEST Rocket Competition).

## Overview
This board serves as the central flight computer and sensor hub, integrating onboard inertial and barometric sensors with dedicated hardware communication interfaces for external GPS, high-g accelerometer, and long-range wireless telemetry modules.

## Hardware Architecture & Key Components
* **Microcontroller:** STMicroelectronics **STM32F407VGTx** (ARM Cortex-M4, LQFP-100) with external crystal oscillator circuit and decoupling/VCAP network.
* **Power Management:** **LM2596S-3.3** step-down switching voltage regulator circuit with Schottky catch diode, power inductor, and bulk filtering capacitors providing a stable **3.3V** rail.
* **Onboard Sensors (I2C1 Bus with 4.7kΩ Pull-ups):**
  * **BNO055:** 9-Axis Absolute Orientation IMU (LGA-28).
  * **MS5611-01BA:** High-Resolution Barometric Pressure & Altitude Sensor (LGA-8).
* **External Module Interfaces:**
  * **SPI1 Header (J1):** Dedicated interface for external high-g accelerometer (**H3LIS331DL**) / flash memory.
  * **UART2 Header (J2):** Serial interface for **NEO-8M** GPS module.
  * **UART3 Header (J3):** Serial interface for **E220-400T30D** LoRa wireless telemetry transceiver.
* **PCB Layout Features:** 2-layer stack-up (`F.Cu` / `B.Cu`) with dual-sided solid Ground (`GND`) copper pours for improved signal integrity and noise reduction.

## Repository Contents
* `Avionics_Flight_Computer_PCB.kicad_pro` – KiCad project file
* `Avionics_Flight_Computer_PCB.kicad_sch` – Complete circuit schematic
* `Avionics_Flight_Computer_PCB.kicad_pcb` – 2-layer PCB layout

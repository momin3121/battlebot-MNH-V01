# battlebot-MNH-V01

## Table of Contents
1. [Introduction](#introduction)
2. [Design Overview](#design-overview)
3. [Weight and Dimensions](#weight-and-dimensions)
4. [Frame Construction](#frame-construction)
5. [tool System](#tool-system)
6. [Electrical Components](#electrical-components)
7. [PCB Design](#pcb-design)
8. [References](#references)

## Introduction
The "battlebot-MNH-V01" is a custom-built battle bot designed for high performance in competitive environments. This bot combines precision engineering and robust construction to achieve high mobility and effective combat capabilities.

![Battle Bot](preview.JPG)

## Design Overview
### Frame Construction
- **Material:** Aluminum
- **Construction:** The frame serves as the skeleton, providing a sturdy yet lightweight base. It includes reinforcements at critical stress points to prevent deformation during combat.
- **Benefits:** The use of aluminum and 3D-printed components allows for rapid prototyping and customization, ensuring flexibility and cost-effectiveness.

![Frame Construction](Detailed-Overhead-View.JPG)

![Frame Construction](Detailed-downhead-View.JPG)

### Weight and Dimensions
- **Total Weight:** 3 kg
- **Overall Dimensions:** 21 cm x 20 cm

## Tool System
### Integration
- **Primary Weapon:** A centrally mounted spinning blade made from hardened steel.
- **Motor:** High-torque electric motor.
- **Specifications:**
  - **Spin Rate:** Up to 5000 RPM
  - **Impact Resistance:** Designed for high durability and easy field repairs.

![Frame Construction](close-look-to-the-tool-mechanism.JPG)

## Electrical Components
### Key Components
- **DC Motor:** High Speed Electric Brush Motor (12V, 100W, 5000RPM)
- **Transmitter:** GoolRC Flysky FS-i6X Transmitter with FS-iA6B Receiver
- **Battery:** CNHL 2200mAh 3S Lipo Battery (30C, 11.1V)
- **Wheels:** Premium 97mm Mecanum Wheels
- **Controller:** ESP32-PICO-D4 microcontroller for managing motor and sensor inputs.

### Motor Drivers
- **Wheel Motors:** Dual L298HN Motor Drivers
- **Weapon Motor:** VNH2SP30 Motor Driver

## PCB Design
### Overview
The PCB (Printed Circuit Board) for the battle bot is designed to control all major functions, including motor control and sensor integration. The design focuses on robustness, efficiency, and ease of maintenance, ensuring optimal performance during competitions.

### Size and Layers
- **Dimensions:** 10 cm x 9.5 cm
- **Layers:** 2-layer design for efficient routing of power and signal traces.

![Frame Construction](PCB-3d-layout.png)

### Trace Widths
- **Motor Traces:** 0.8 mm (for currents up to 2A)
- **Tool  Motor Traces:** 2.5 mm (for currents up to 10A)
- **Design Standards:** Trace widths are calculated based on IPC-2221 standards to handle the expected current loads with an allowable temperature rise of 10°C to 20°C.

### Key Components
- **Microcontroller (U3):** ESP32-PICO-D4
  - **Function:** Central processing unit that handles control logic, motor commands, and sensor inputs.
  - **Power Supply:** 3.3V provided by AMS1117-3.3 voltage regulator.
- **Motor Drivers:**
  - **L298HN (U1, U5):** Controls the four wheel motors, allowing precise movement and speed adjustments.
  - **VNH2SP30 (U2):** Manages the high-current weapon motor, providing necessary torque and speed.
- **Voltage Regulator (U6):** AMS1117-3.3
  - **Function:** Provides stable 3.3V output for low-power devices.
  - **Current Handling:** Up to 1A, supporting the microcontroller and sensors.
- **USB to Serial Converter (U4):** CH340E
  - **Function:** Enables programming and communication between the microcontroller and a computer.
- **Capacitors (C1, C10-C16):** Stabilize voltage and filter noise in the power supply.
- **Resistors (R1, R2, R3, R4, R6):** Employed for pulling up/down inputs and limiting current to protect other components.
- **Connectors (J1, J2, J3, J4, J5, J6):** Provide interfaces for external connections to motors, power sources, and other peripherals.
- **Switch (SW1):** Used to enable the microcontroller, typically controlling the power state or activation of the system.

![Frame Construction](schematic-deisgn.pdf)

### Power Management
- **AMS1117-3.3 Voltage Regulator (U6):**
  - **Function:** Provides a stable 3.3V output for low-power devices.
  - **Current Handling:** Up to 1A.
  - **Integration:** Positioned near power inputs with filtering capacitors to ensure smooth operation.
- **VNH2SP30 Motor Driver:**
  - **Function:** Drives the weapon motor.
  - **Current Handling:** 30A continuous.
  - **Integration:** Includes extensive heat sinking to manage high current loads.
- **Dual L298HN Motor Drivers:**
  - **Function:** Independently controls four wheel motors.
  - **Current Handling:** 2A per channel.
  - **Integration:** Equipped with dedicated capacitors for voltage stabilization and noise filtering.

### Layout and Design Considerations
- **Trace Width:** Motor traces are designed to handle high currents without excessive heat buildup or voltage drop.
- **Via Optimization:** Used to connect traces between the top and bottom layers, enhancing electrical performance.
- **Accessibility:** All connectors and critical components are easily accessible for maintenance and troubleshooting.

![Frame Construction](PCB-design.png)

## References
1. [High Power DC Motor](https://www.amazon.com/Power-12V-24V-Torque-Bearing-Driver/dp/B086Z47DLJ)
2. [GoolRC Flysky FS-i6X Transmitter](https://www.amazon.com/dp/B0872QHMM3)
3. [CNHL 2200mAh 3S Lipo Battery](https://www.amazon.com/CNHL-2200mAh-Battery-Airplane-Quadcopter/dp/B0BTYPT4RT)
4. [Zeberoxyz GT2 Synchronous Wheel Set](https://www.amazon.com/Zeberoxyz-Synchronous-Aluminum-Timing-20-60T-8B-6/dp/B08QZ4365D)
5. [Premium Mecanum Wheels](https://www.amazon.com/Directional-Coupling-Connector-Raspberry-Microbit/dp/B09KY6C5BG)
6. [VNH2SP30 Motor Driver](https://www.snapeda.com/parts/VNH2SP30-E/STMicroelectronics/view-part/)
7. [L298N Motor Driver](https://www.snapeda.com/parts/L298N/STMicroelectronics/view-part/)
8. [ESP32-PICO-D4 MCU](https://www.snapeda.com/parts/ESP32-PICO-D4/Espressif%20Systems/view-part/)

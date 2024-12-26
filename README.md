# ESP32-Based Autonomous Car with Live Camera Feed

![ESP32 Car](https://github.com/user-attachments/assets/87097c50-60c2-4ba0-abbe-e1990cc93dec)

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Hardware Components](#hardware-components)
- [Circuit Diagram](#circuit-diagram)
- [Software Requirements](#software-requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

## Overview

This project showcases an ESP32-based autonomous car equipped with a live camera feed. The car can be controlled remotely via a web interface, allowing users to maneuver the car, adjust speed, control lighting, and manipulate the camera's pan and tilt functions in real-time. The system leverages WebSockets for seamless communication between the client and the ESP32 server, ensuring responsive and interactive control.

## Features

- **Remote Control**: Move the car forward, backward, left, right, and stop using on-screen buttons.
- **Adjustable Speed**: Modify the car's speed using a slider.
- **Lighting Control**: Illuminate the car with adjustable brightness.
- **Pan & Tilt Camera**: Control the camera's orientation to capture different angles.
- **Live Camera Feed**: View real-time video from the car's camera directly in the web interface.
- **WebSocket Communication**: Ensures real-time, bidirectional communication between the web interface and the ESP32.
- **Servo Control**: Smoothly control the pan and tilt servos for optimal camera positioning.

## Hardware Components

- **ESP32 Dev Board**: The core microcontroller managing all functionalities.
- **Dual DC Motors**: For driving the car.
- **Motor Driver (e.g., L298N)**: To control the motor operations.
- **Servo Motors**: For pan and tilt functionalities of the camera.
- **ESP32-CAM Module**: Provides the camera feed.
- **Power Supply**: Appropriate power source for the ESP32 and motors.
- **Jumper Wires**: For making connections between components.
- **Chassis**: To assemble all components into a mobile platform.
- **Miscellaneous**: Breadboard, resistors, capacitors, etc., as needed.

## Circuit Diagram

![Circuit Diagram](https://github.com/user-attachments/assets/ff032c08-1e67-4027-a1b1-7de7f595db69)

*Refer to the above diagram for connecting all components correctly.*

## Software Requirements

- **Arduino IDE**: [Download Here](https://www.arduino.cc/en/software)
- **ESP32 Board Support**: Install via the Arduino Boards Manager.
- **Required Libraries**:
  - `ESPAsyncWebServer`
  - `AsyncTCP`
  - `ESP32Servo`
  - `esp_camera.h`
  - `vector` (Standard C++ Library)

## Installation

### 1. Setup Arduino IDE for ESP32

1. **Install ESP32 Board in Arduino IDE**:
   - Open Arduino IDE.
   - Go to `File` > `Preferences`.
   - In the "Additional Boards Manager URLs" field, add:
     ```
     https://dl.espressif.com/dl/package_esp32_index.json
     ```
   - Navigate to `Tools` > `Board` > `Boards Manager`.
   - Search for "ESP32" and install the latest version.

### 2. Install Required Libraries

- **ESPAsyncWebServer**:
  1. Download from [GitHub](https://github.com/me-no-dev/ESPAsyncWebServer).
  2. Install via Arduino IDE by navigating to `Sketch` > `Include Library` > `Add .ZIP Library`.
  
- **AsyncTCP**:
  1. Download from [GitHub](https://github.com/me-no-dev/AsyncTCP).
  2. Install similarly as above.
  
- **ESP32Servo**:
  1. Available through the Arduino Library Manager.
  2. Go to `Sketch` > `Include Library` > `Manage Libraries`.
  3. Search for "ESP32Servo" and install.

### 3. Clone the Repository

```bash
git clone https://github.com/yourusername/esp32-autonomous-car.git
```

## Usage

1. **Power On**: Connect the power supply to the ESP32 and motors.
2. **Connect to Wi-Fi**:
   - On your device (smartphone/laptop), search for a Wi-Fi network named `MyWiFiCar`.
   - Connect using the password `12345678`.
3. **Access Web Interface**:
   - Open a web browser and navigate to `http://192.168.4.1`.
   - You should see the control interface with buttons and sliders.
4. **Control the Car**:
   - Use the arrow buttons to move the car.
   - Adjust speed, lighting, pan, and tilt using the sliders.
   - View the live camera feed in the designated area.

## Project Structure

- **code.ino**: The primary Arduino sketch for the ESP32, handling Wi-Fi, motor control, and WebSocket communication.
- **readme.md**: Detailed documentation of the project.
- **LICENSE**: Licensing information for the project.
- **hardware/**: Contains schematics and hardware-related files, including the circuit diagram.
- **software/**: Houses software components, including libraries and dependency lists.
- **assets/**: Contains assets such as images and CSS files used in the project.

## Troubleshooting

- **Camera Initialization Failed**:
  - Ensure all camera pins are correctly connected.
  - Verify that the ESP32-CAM is compatible with your board.
  - Check for an adequate power supply to the camera module.

- **Web Interface Not Loading**:
  - Confirm that your device is connected to the `MyWiFiCar` network.
  - Check the serial monitor for any connectivity issues.
  - Ensure that the ESP32 is successfully running the uploaded code.

- **Motors Not Responding**:
  - Double-check motor connections and pin assignments.
  - Ensure that the motor driver is receiving sufficient power.
  - Verify that the correct PWM channels are being used.

- **Slow Camera Feed**:
  - Adjust the `jpeg_quality` and `frame_size` in the camera configuration to optimize performance.
  - Ensure that the network connection is stable and has sufficient bandwidth.

- **Servo Movement Issues**:
  - Verify that the servos are properly connected to the correct pins.
  - Check for any mechanical obstructions that might prevent servo movement.

## Contributing

Contributions are welcome! Please follow these steps:

1. **Fork the Repository**:
   - Click the "Fork" button at the top-right corner of the repository page.

2. **Create a New Branch**:
   ```bash
   git checkout -b feature/YourFeature
   ```

3. **Commit Your Changes**:
   ```bash
   git commit -m "Add your message"
   ```

4. **Push to the Branch**:
   ```bash
   git push origin feature/YourFeature
   ```

5. **Open a Pull Request**:
   - Navigate to the original repository.
   - Click on the "Compare & pull request" button.
   - Provide a descriptive title and detailed description of your changes.

### Guidelines

- **Code Quality**: Ensure your code follows the project's coding standards and is well-documented.
- **Testing**: Test your changes thoroughly before submitting.
- **Issue Reporting**: If you find a bug or have a feature request, please open an issue first.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

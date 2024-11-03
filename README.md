# Smart Agriculture System 🌱

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-STM32-green)]()
[![IoT](https://img.shields.io/badge/IoT-Agriculture-brightgreen)]()

A comprehensive IoT-based solution for modern agriculture that combines real-time monitoring of environmental parameters with machine learning for plant disease detection. Designed to aid farmers and agricultural engineers in making informed decisions and improving crop yields.

---

## Table of Contents
- [Project Overview](#project-overview)
- [System Architecture](#system-architecture)
- [Features](#features)
- [Hardware Components](#hardware-components)
- [Software Components](#software-components)
- [Data Flow](#data-flow)
- [Installation Guide](#installation-guide)
- [How to Use](#how-to-use)
- [Plant Disease Detection Model](#plant-disease-detection-model)
- [Demo and Screenshots](#demo-and-screenshots)
- [Contributing](#contributing)
- [License](#license)

---

## Project Overview
The Smart Agriculture System utilizes embedded systems and IoT technologies to:
1. **Monitor** environmental factors like soil moisture, temperature, and humidity.
2. **Analyze** data to ensure optimal growing conditions.
3. **Detect** plant diseases using a CNN model trained on a diverse dataset of plant images.
4. **Alert** users when conditions fall outside optimal ranges or diseases are detected.

## System Architecture
The system integrates hardware and software components:
- **STM32L475 Microcontroller** serves as the main processor, collecting data from sensors and handling communication.
- **Sensors** monitor environmental data such as soil moisture, air temperature, humidity, and light.
- **Communication Module (MQTT)** allows real-time data transfer to a central monitoring system, enabling remote access.
- **Machine Learning Module (CNN)** analyzes images to detect potential plant diseases.

---

## Features
- **Environmental Monitoring**: 
  - Real-time tracking of soil moisture, temperature, light intensity, and humidity.
- **Disease Detection**:
  - CNN model identifies common plant diseases based on leaf images.
- **Remote Monitoring**:
  - Data is sent via MQTT to a web-based interface where users can track real-time conditions.
- **Automated Alerts**:
  - Notifications sent to the user if environmental parameters fall outside acceptable thresholds.

---

## Hardware Components
- **Microcontroller**: STM32L475, selected for its low power consumption and efficient data processing capabilities.
- **Sensors**:
  - Soil moisture sensor
  - DHT11/DHT22 for temperature and humidity
  - LDR (Light Dependent Resistor) for light intensity
- **Communication Module**: ESP8266 or similar module for MQTT protocol compatibility.
- **Camera Module**: Used to capture plant images for disease detection.

---

## Software Components
- **Firmware**:
  - C/C++ code running on the STM32 to manage sensor data collection and communication.
- **Machine Learning Model**:
  - A Convolutional Neural Network (CNN) model trained on the Kaggle Plant Disease dataset.
- **MQTT Broker**:
  - A server to manage data transfers, such as Mosquitto MQTT broker.
- **Web Dashboard**:
  - Interface for remote monitoring, built with Node.js or Flask for backend, and a frontend in React.js or a similar framework.

---

## Data Flow
1. **Data Collection**:
   - Sensors read environmental data.
2. **Data Transmission**:
   - STM32 sends data to the MQTT broker.
3. **Data Processing**:
   - Data from MQTT broker is displayed on the web interface.
4. **Image Analysis**:
   - Captured plant images are processed by the CNN model to detect diseases.
5. **Alerts**:
   - If anomalies are detected, alerts are triggered on the web dashboard.

---

## Installation Guide
### 1. Hardware Setup
   - Connect the STM32L475 microcontroller to the sensors.
   - Ensure stable power and network connectivity for the communication module.
   - Test each sensor individually to ensure proper functionality.

### 2. Software Setup
   - **Firmware**:
     - Use PlatformIO to write and upload firmware to STM32.
   - **CNN Model**:
     - Download the trained model and place it in the `/models` directory.
   - **MQTT Broker**:
     - Install Mosquitto (or any MQTT broker) for data handling.
   - **Web Dashboard**:
     - Set up the dashboard server and ensure it connects to the MQTT broker.

---

## How to Use
1. **Starting the System**:
   - Power up the STM32, connect to the sensors, and ensure the communication module is ready.
2. **Data Collection**:
   - Data will automatically start flowing to the MQTT broker and be displayed on the web interface.
3. **Disease Detection**:
   - Upload plant images periodically or set up automated image capture. The CNN model will analyze the images and notify users if diseases are detected.
4. **Monitoring and Alerts**:
   - Log into the web dashboard to track real-time data and respond to alerts.

---

## Plant Disease Detection Model
The CNN model used in this project was trained using the [Plant Disease Dataset](https://www.kaggle.com/datasets/vipoooool/new-plant-diseases-dataset) on Kaggle. Key details:
- **Model Architecture**: Convolutional Neural Network with multiple convolutional and pooling layers.
- **Training**: Achieved high accuracy by using data augmentation techniques.
- **Deployment**: The model is optimized for real-time inference, capable of processing images and predicting disease presence efficiently.

---

## Demo and Screenshots
Images and video demonstrations are available in the `/demo` folder. Below is a sample of the system interface and live monitoring features.

![System Interface Screenshot](images/interface.png)

---

## Contributing
Contributions are welcomed! Follow these steps to contribute:
1. Fork the repository and clone it locally.
2. Create a new branch for your feature or bug fix.
3. Submit a pull request with a description of changes.

Please see the `CONTRIBUTING.md` for detailed guidelines on submitting improvements.

---

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for full details.

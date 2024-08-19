# Time-Lapse Box Project

## Project Overview
The **Time-Lapse Box** was developed to monitor environmental changes over time by capturing images from a fixed perspective at regular intervals. This allows for the visualization of gradual changes, such as those caused by urban growth, pollution, or climate change. The device is self-sufficient, operating on battery power, and can be placed in remote locations. It also measures environmental parameters like temperature and air quality.

## Technologies and Components Used

### Hardware
- **Raspberry Pi 2 Model B**: The primary computing unit responsible for capturing images, processing them with OpenCV, and storing data on a USB stick.
- **Pi Camera Module**: A 5MP camera connected to the Raspberry Pi for high-resolution image capture.
- **ATmega328P Microcontroller**: Manages sensors and power efficiency, activating only when necessary to conserve battery life.
- **Honeywell Laser Particle Sensor**: Measures particulate matter (PM2.5 and PM10) for air quality analysis.
- **DS1307 Real-Time Clock (RTC)**: Ensures accurate timing for image capture and sensor readings, while minimizing power consumption.
- **BMP280 Sensor**: Measures atmospheric pressure and temperature.
- **Power Supply**: Composed of six 3.7V batteries, configured for optimized capacity and voltage to power the system.

### Software
- **Raspberry Pi OS Lite**: A lightweight operating system on the Raspberry Pi, chosen for low resource consumption.
- **OpenCV**: Used for image processing to evaluate sharpness and brightness, ensuring only high-quality images are stored.
- **Python**: The main programming language for camera control, image processing, and sensor data management.

### Communication and Data Handling
- **UART (Universal Asynchronous Receiver-Transmitter)**: Handles communication between the Raspberry Pi, ATmega328P microcontroller, and Honeywell sensor.
- **Mobile Connectivity**: Sends status updates to a server via mobile network, allowing remote monitoring of the box's status.

## Project Implementation
The Time-Lapse Box is designed for energy efficiency, with the Raspberry Pi remaining off most of the time, only activating when it's time to capture and process an image. The microcontroller manages power, turning on components as needed. Captured images and sensor data are stored on a USB stick for easy retrieval.

## Key Challenges and Future Work
- **Power Management**: While a solar panel was considered for extended operation, it was excluded due to time constraints. Future improvements could explore solar power or other renewable energy sources.
- **Sensor Integration**: Due to UART port limitations, the Honeywell sensor was connected to the Raspberry Pi instead of the ATmega328P. Future versions might use a microcontroller with multiple UART interfaces to handle more sensors efficiently.
- **Real-Time Clock Accuracy**: The DS1307 RTC may drift over time, requiring periodic recalibration against an internet time server, which could be a future enhancement.

This project effectively combines embedded systems, power management, and environmental monitoring to observe and document environmental changes in remote locations.

# Footstep Energy Harvesting System

An IoT-based voltage monitoring project that uses an ESP32 to read voltage signals, display measurements on an I2C LCD, and transmit data to ThingSpeak for cloud monitoring through a web dashboard hosted on Vercel.

## Project Overview

This project explores the integration of embedded systems, wireless communication, cloud data storage, and web technologies for monitoring voltage in a footstep energy harvesting setup.

The ESP32 reads an analog voltage signal, displays the measured voltage on a local LCD, and uploads readings to ThingSpeak over Wi-Fi. A web dashboard provides an interface for viewing voltage readings and their history.

## Features

- Voltage monitoring using ESP32 GPIO34.
- Local voltage display using a 16×2 I2C LCD.
- Wireless data transmission over Wi-Fi.
- Cloud data storage using ThingSpeak.
- Web dashboard hosted on Vercel.
- Periodic retrieval and visualization of voltage readings.

## Live Dashboard

Website: https://footstep-energy.vercel.app/

## Hardware Requirements

- ESP32 Dev Module
- Voltage sensor or appropriately conditioned voltage signal
- 16×2 I2C LCD
- Footstep energy harvesting setup
- Jumper wires and connecting components
- USB cable and power supply

**Safety note:** Ensure the voltage supplied to the ESP32 analog input remains within its permitted input range. Use appropriate signal conditioning where necessary.

## Technologies Used

- Arduino IDE
- C++
- ESP32 Arduino Core
- Wire library
- LiquidCrystal_I2C library
- ThingSpeak
- HTML, CSS and JavaScript
- Vercel

## System Architecture

```text
Footstep Energy Harvesting Setup
              |
              v
      Voltage Signal Input
              |
              v
        ESP32 GPIO34
              |
        +-----+------+
        |            |
        v            v
     I2C LCD        Wi-Fi
   Local Display      |
                      v
                  ThingSpeak
                      |
                      v
                Vercel Dashboard
```

## Working Principle

1. The voltage signal is connected to the ESP32 GPIO34 analog input.
2. The ESP32 reads the analog input and calculates a voltage estimate.
3. The voltage reading is displayed on the I2C LCD.
4. The ESP32 connects to Wi-Fi and sends voltage data to ThingSpeak.
5. The web dashboard retrieves the cloud data and displays the readings.

## ThingSpeak Configuration

The project uses ThingSpeak to store voltage readings.

- Channel ID: `3546179`
- Field 1: Voltage

The latest Field 1 reading can be retrieved using the following endpoint:

```text
https://api.thingspeak.com/channels/3546179/feeds/last.json
```

Keep ThingSpeak write API keys and Wi-Fi credentials private. Do not commit credentials to a public repository.

## Installation and Setup

### 1. Configure the ESP32

1. Open the firmware in Arduino IDE.
2. Install the required LCD library.
3. Select ESP32 Dev Module as the target board.
4. Configure Wi-Fi credentials and the ThingSpeak write API key locally.
5. Verify the voltage input and LCD connections.
6. Compile and upload the firmware.

### 2. Configure ThingSpeak

1. Create or open the ThingSpeak channel.
2. Enable Field 1 for voltage data.
3. Configure the ESP32 firmware with the channel's write API key.
4. Confirm that voltage readings are appearing in the channel.

### 3. Deploy the Dashboard

1. Add the dashboard's HTML, CSS and JavaScript files to the repository.
2. Ensure that the deployment serves the intended homepage, usually `index.html`.
3. Configure the dashboard to retrieve readings from the ThingSpeak channel.
4. Deploy the website using Vercel.
5. Verify that the displayed readings correspond to the cloud data.

## Expected Output

The system is designed to provide:

- Voltage readings on the local LCD.
- Periodic voltage updates to ThingSpeak.
- Cloud-based access to stored voltage measurements.
- A web dashboard for viewing recent readings and voltage history.

Actual measurements depend on the connected input, sensor circuit, calibration and harvesting setup.

## Future Enhancements

- Improve voltage measurement accuracy through calibration.
- Add voltage trend analysis and historical charts.
- Integrate current measurement to estimate power and energy.
- Introduce configurable voltage threshold alerts.
- Improve dashboard responsiveness and visualization.

## Applications

- Embedded systems and IoT education.
- Footstep energy harvesting demonstrations.
- Voltage monitoring prototypes.
- Cloud-connected sensor applications.

## Project Information

- Project: Footstep Energy Harvesting System
- Microcontroller: ESP32 Dev Module
- Cloud Platform: ThingSpeak
- Dashboard Hosting: Vercel

## License

No license has been specified for this repository yet.

# ESP32 Virtual Smart Weather Station via MQTT

A zero-budget IoT and embedded systems project simulating an industrial Smart Weather Station. This project demonstrates hardware-software integration, cloud data streaming, and efficient firmware architecture without relying on physical hardware components.

## 🚀 Live Simulation & Interactive Demo
You can test, modify, and run this circuit interactively directly in your browser:
👉 (https://wokwi.com/projects/466820197913635841)

*(Note: Click the **Play** button, then click on the light-blue DHT22 sensor element during the runtime simulation to manually adjust the temperature/humidity sliders and watch the real-time data push).*

## 🛠️ Tech Stack & Architecture
- **Hardware Simulator:** Wokwi
- **Microcontroller:** ESP32 (WROOM DevKit v1)
- **Sensor Infrastructure:** DHT22 (High-accuracy Temperature & Humidity)
- **Messaging Protocol:** MQTT (Message Queuing Telemetry Transport)
- **Cloud Infrastructure:** HiveMQ Public MQTT Broker
- **Firmware Development:** C/C++ (Arduino Framework Architecture)

## 📡 System Workflow & Implementation
1. **Network Initialization:** The ESP32 framework configures a virtual station mode (`WIFI_STA`) to safely lease a secure network handshake over the local virtual gateway.
2. **Telemetry Reading:** A timed asynchronous routine fetches localized environment metadata via digital communication pins, maintaining a non-blocking execution loop (omitting traditional hardware-freezing delays).
3. **Data Serialization:** Dynamic float outputs are parsed and formatted into stable payload strings to prevent buffer overruns or data package corruption.
4. **Cloud Publish:** Utilizing a `PubSubClient` configuration, the serialized network packets are dispatched to distinct topic nodes (`ameliabelanda/weather/...`) hosted on the HiveMQ broker, allowing any remote web clients to instantly consume real-time sensor streams.

## 📂 Repository Contents
- `sketch.ino` - Core embedded C++ production code containing connection-loss recovery routines, memory management, and hardware peripherals initialization.
- `diagram.json` - Virtual schematic blueprint mapped out for the Wokwi execution engine.

# Smart Waste Segregation — Recovered ESP32 Controller

This folder contains a cleaned, reconstructed ESP32 servo-controller sketch based on the implementation listing in the internship report supplied for this project (printed pages 9–10; PDF pages 13–14).

## Included source

- `esp32_servo_controller.ino`: an ESP32 Wi-Fi server that receives a recyclable / not-recyclable command and moves a servo to the corresponding sorting position.

## Hardware and libraries mentioned in the report

- ESP32 board (the implementation uses `WiFi.h`; despite the report heading saying “Arduino Uno”, this listing is written for ESP32)
- Servo motor connected to GPIO 12
- `ESP32Servo` library
- Wi-Fi network

The report also discusses a camera, conveyor belt, ultrasonic sensor, Raspberry Pi / Arduino, YOLO object detection, OpenCV, and communication between the detection and controller components. It does not include the complete Python YOLO source, model weights, dataset, or a complete wiring diagram.

## Configure and test

1. Install Arduino IDE and ESP32 board support.
2. Install the `ESP32Servo` library.
3. Open `esp32_servo_controller.ino`.
4. Replace `YOUR_WIFI_SSID` and `YOUR_WIFI_PASSWORD` with your local test network credentials. Do not commit real credentials.
5. Select the correct ESP32 board and port, then upload.
6. Open Serial Monitor at `115200` baud and note the ESP32 IP address.
7. From a device on the same network, test:
   - `http://<ESP32-IP>:8080/recyclable`
   - `http://<ESP32-IP>:8080/not-recyclable`

The HTTP endpoints are a small reconstruction to make the controller testable. They are not reproduced verbatim from the report's original request-handling code.

## Recovery notes

- The original report prints Wi-Fi credentials in its code listing. Those values have intentionally not been copied here. Change the Wi-Fi password if the credentials shown in the report are still active.
- The report has a hardware-description mismatch: its abstract describes a sensor-less approach, while the methodology mentions an ultrasonic sensor; the implementation code uses ESP32 Wi-Fi and a servo, despite being labelled “Arduino Uno”. Confirm the actual hardware configuration before presenting this as a final project.
- The Python YOLO detection program is not present in the supplied report. This folder must not be described as the complete end-to-end YOLO + IoT project until that source and the actual model/configuration are recovered or rebuilt and tested.

## Status

Recovered controller example — not a verified complete system. Check servo angles, GPIO mapping, power supply, and mechanical positions against the actual hardware before operating a physical sorting mechanism.

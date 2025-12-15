## Introduction
This project demonstrates how to build an IoT-based weather monitoring system using an ESP32 microcontroller and a BMP280 sensor. The ESP32 collects environmental data such as temperature, pressure, and altitude from the BMP280 sensor through I2C communication. After collecting the data, the system connects to Wi-Fi and uploads the readings to an InfluxDB time-series database using a lightweight data protocol (HTTP or MQTT, depending on implementation).

InfluxDB stores the sensor telemetry with timestamps for fast querying and historical analysis. For real-time monitoring and visualization, Grafana is connected directly to InfluxDB to display live dashboards and time-series graphs. Additionally, a mobile application built with MIT App Inventor allows users to view current readings and basic trends from a smartphone, providing an easy on-the-go monitoring option without needing to open Grafana.

## Objective
The objectives of this Lab 5 project are to:

  * Interface the BMP280 sensor with the ESP32 using I2C in MicroPython.

  * Read temperature, pressure, and altitude values from the BMP280.

  * Connect the ESP32 to Wi-Fi using MicroPython network libraries.

  * Publish the collected sensor data to InfluxDB for time-series storage.

  * Monitor and visualize real-time sensor data using Grafana dashboards.

  * Provide a mobile monitoring interface using MIT App Inventor to display live readings and recent history.

## Software Requirement
To complete this lab, the following software/tools are required:

  * Thonny IDE (for coding and uploading to ESP32)

  * MicroPython firmware installed on ESP32

  * InfluxDB (local server or cloud instance for data storage)

  * Grafana (connected to InfluxDB for real-time visualization)

  * MIT App Inventor (for building the mobile monitoring app)

## Setup Instruction
1. Step 1: Flash MicroPython

  * Connect ESP32 to your computer via USB.

  * Open Thonny IDE.

  * Go to: Tools → Options → Interpreter

  * Select: MicroPython (ESP32)

  * Ensure the MicroPython firmware is installed and active.

2. Step 2: Upload Required Files

  * Upload main.py into the ESP32.

  * Upload bmp280.py library into the same directory.

  * Both files must be on the board for the project to run correctly.

3. Step 3: Configure InfluxDB

* Start InfluxDB (local or cloud).

* Create a bucket/database for sensor data (example: weather_bucket).

* Generate a write-access API token.

4.  Step 4: Configure Wi-Fi
  * Update the Wi-Fi credentials in main.py

5. Step 5: Connect Grafana to InfluxDB

  * Open Grafana and log in.

    * Go to: Data Sources → Add data source → InfluxDB.

    * Enter the InfluxDB URL, bucket, org, and token.

    * Import or create a dashboard with panels for:

    * Temperature

    * Pressure

    * Altitude

6. Step 6: Prepare MIT App Inventor App

* Open the project in MIT App Inventor (or create a new one).

* Add UI components (labels/charts/buttons) to display readings.

* In Blocks, set the API endpoint that reads data from InfluxDB (typically via a small backend or InfluxDB query API).

* Build the APK and install it on an Android phone.

* Wiring Connection (BMP280 → ESP32)

BMP280 Pin	ESP32 Pin
VCC	3.3V
GND	GND
SDA	GPIO 21
SCL	GPIO 22

## Usage Instruction

* Connect the ESP32 to your computer and run main.py in Thonny.

* Open the Serial Monitor to check status messages:

* Wi-Fi connection success

* Sensor readings

* InfluxDB write/publish confirmation

* Go to InfluxDB Data Explorer (or query view).

* Confirm that temperature, pressure, and altitude data points are arriving with timestamps.

* Open Grafana → Your Weather Dashboard.

* You should see temperature, pressure, and altitude updating in real time.

* Adjust the time range (last 5 min, 1 hour, 24 hours) to view trends.

* Open the MIT App Inventor mobile app on your phone.

* Tap Refresh / Get Data to load the latest readings.

## Video URL
https://youtube.com/shorts/vav6QG6bXLY?feature=share

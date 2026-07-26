# NodeMCU ESP8266 Firmware

This firmware receives attendance data from Arduino UNO and uploads it to Google Sheets.

---

## Features

- Wi-Fi Connection
- HTTPS Communication
- Google Apps Script Integration
- Login & Logout Upload
- Automatic Reconnection
- Error Handling

---

## Required Libraries

- ESP8266WiFi
- ESP8266HTTPClient
- WiFiClientSecure

---

## Board

NodeMCU 1.0 (ESP-12E Module)

---

## Baud Rate

9600

---

## Data Format

Arduino sends:

UID,Name,LOGIN

Example:

53317856,Manasa,LOGIN

NodeMCU uploads:

Name
UID
Date
Login Time
Logout Time
Status

to Google Sheets.
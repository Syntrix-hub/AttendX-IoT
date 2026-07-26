# AttendX-IoT
# Smart RFID Attendance System using Arduino UNO, NodeMCU ESP8266 and Google Sheets

A low-cost IoT-based Smart Attendance System that records student attendance using RFID cards and stores Login/Logout data automatically in Google Sheets through Wi-Fi.

---

## Features

- RFID Based Attendance
- Google Sheets Integration
- Automatic Login & Logout
- Date & Time Logging
- Green LED for Valid Card
- Red LED for Invalid Card
- LCD Display
- Buzzer Notification
- Real-Time Cloud Storage
- Wi-Fi Enabled
- Easy to Expand

---

## Hardware Used

- Arduino UNO
- NodeMCU ESP8266
- MFRC522 RFID Reader
- RFID Cards
- 16x2 I2C LCD
- Green LED
- Red LED
- Active Buzzer
- Breadboard
- Jumper Wires
- USB Cable

---

## Software Used

- Arduino IDE
- Google Apps Script
- Google Sheets

---

## Circuit Connections

### RFID

| RFID | Arduino |
|-------|----------|
| SDA | D10 |
| SCK | D13 |
| MOSI | D11 |
| MISO | D12 |
| RST | D9 |
| 3.3V | 3.3V |
| GND | GND |

### LCD

| LCD | Arduino |
|------|----------|
| SDA | A4 |
| SCL | A5 |
| VCC | 5V |
| GND | GND |

### LEDs

Green LED -> D6

Red LED -> D5

Buzzer -> D7

### NodeMCU

Arduino TX -> NodeMCU RX (Voltage Divider)

Arduino GND -> NodeMCU GND

---

## Project Workflow

1. Student scans RFID card
2. RFID Reader reads UID
3. Arduino verifies UID
4. LCD displays student name
5. Green LED glows
6. Arduino sends UID and Name to NodeMCU
7. NodeMCU connects to Google Apps Script
8. Attendance stored in Google Sheets
9. Login/Logout updated automatically

---

## Google Sheet Format

| Name | UID | Date | Login Time | Logout Time | Status |

---

## Project Structure

Arduino UNO
↓

RFID Verification

↓

NodeMCU ESP8266

↓

Wi-Fi

↓

Google Apps Script

↓

Google Sheets

---

## Future Improvements

- Face Recognition
- Fingerprint Authentication
- Mobile Application
- Firebase Integration
- Attendance Dashboard
- SMS Notification
- Email Alerts
- QR Code Attendance
- Cloud Database
- Analytics Dashboard

---

## Developed By

Nandan Kumar M
Computer Science Engineering

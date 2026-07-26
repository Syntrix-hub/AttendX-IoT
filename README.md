# 📡 Smart RFID Attendance System using Arduino UNO, NodeMCU ESP8266 & Google Sheets

![Arduino](https://img.shields.io/badge/Arduino-UNO-blue?logo=arduino)
![ESP8266](https://img.shields.io/badge/ESP8266-NodeMCU-green)
![RFID](https://img.shields.io/badge/RFID-MFRC522-orange)
![IoT](https://img.shields.io/badge/IoT-Attendance-red)
![License](https://img.shields.io/badge/License-MIT-yellow)

An IoT-based Smart Attendance System that automates attendance recording using RFID technology. The system authenticates users through RFID cards, displays attendance status on an LCD, provides LED and buzzer feedback, and uploads attendance records (Login & Logout) to Google Sheets via the NodeMCU ESP8266.

---

# 📖 Project Overview

Traditional attendance systems require manual effort and are prone to errors. This project provides an automated attendance solution using RFID technology integrated with cloud storage.

When a registered RFID card is scanned:

- The RFID UID is verified.
- Student information is displayed on the LCD.
- Green LED and buzzer indicate successful authentication.
- Attendance is uploaded to Google Sheets.
- Login and Logout are automatically recorded.

Unregistered RFID cards are rejected using a red LED and warning buzzer.

---

# 🚀 Features

✅ RFID-based Authentication

✅ Automatic Login & Logout

✅ Google Sheets Cloud Storage

✅ Real-time Attendance Tracking

✅ LCD Display

✅ Green LED for Valid Users

✅ Red LED for Invalid Users

✅ Buzzer Notification

✅ Wi-Fi Enabled

✅ Date & Time Logging

✅ Easy Student Registration

✅ Low Cost IoT Solution

---

# 🛠 Hardware Requirements

| Component | Quantity |
|-----------|----------|
| Arduino UNO | 1 |
| NodeMCU ESP8266 | 1 |
| MFRC522 RFID Reader | 1 |
| RFID Cards/Tags | As Required |
| 16x2 I2C LCD | 1 |
| Green LED | 1 |
| Red LED | 1 |
| Active Buzzer | 1 |
| Breadboard | 1 |
| Jumper Wires | Several |
| USB Cable | 2 |

---

# 💻 Software Requirements

- Arduino IDE
- Google Chrome
- Google Apps Script
- Google Sheets
- ESP8266 Board Package
- Git
- GitHub

---

# 📚 Required Libraries

Arduino UNO

- SPI
- Wire
- MFRC522
- LiquidCrystal_I2C

NodeMCU

- ESP8266WiFi
- ESP8266HTTPClient
- WiFiClientSecure

---

# 🔌 Circuit Connections

## RFID (MFRC522)

| RFID | Arduino UNO |
|-------|-------------|
| SDA | D10 |
| SCK | D13 |
| MOSI | D11 |
| MISO | D12 |
| RST | D9 |
| GND | GND |
| 3.3V | 3.3V |

---

## LCD (I2C)

| LCD | Arduino UNO |
|------|-------------|
| SDA | A4 |
| SCL | A5 |
| VCC | 5V |
| GND | GND |

---

## LEDs

Green LED → D6

Red LED → D5

---

## Buzzer

Positive → D7

Negative → GND

---

## Arduino UNO ↔ NodeMCU

| Arduino | NodeMCU |
|----------|----------|
| TX (D1) | RX (GPIO3) *(through a voltage divider or logic-level converter)* |
| GND | GND |

> **Note:** The Arduino UNO TX pin outputs 5 V logic, while the NodeMCU RX pin is 3.3 V tolerant. Use a voltage divider or logic-level converter to protect the NodeMCU.

---

# 📂 Project Structure

```
Smart-RFID-Attendance-System
│
├── Arduino_UNO/
│      RFID_Attendance.ino
│
├── NodeMCU_ESP8266/
│      GoogleSheetsUploader.ino
│
├── Google_Apps_Script/
│      Code.gs
│
├── Circuit/
│
├── Images/
│
├── Documents/
│
├── README.md
├── LICENSE
└── .gitignore
```

---

# ⚙ Working Principle

1. Power ON the system.
2. RFID Reader waits for a card.
3. User scans RFID card.
4. Arduino reads RFID UID.
5. UID is compared with stored IDs.
6. LCD displays student name.
7. Green LED turns ON.
8. Buzzer beeps.
9. Arduino sends UID & Name to NodeMCU.
10. NodeMCU connects to Wi-Fi.
11. Attendance data is uploaded using Google Apps Script.
12. Google Sheets stores Login or Logout with date and time.

For an invalid card:

- LCD displays **Access Denied**
- Red LED turns ON
- Buzzer gives an alert

---

# ☁ Google Sheets Format

| Name | UID | Date | Login Time | Logout Time | Status |
|------|------|------|------------|-------------|--------|
| Manasa | 53317856 | 26-07-2026 | 09:15:20 | 05:30:15 | Present |

---

# 📷 Screenshots

Add the following images inside the **Images** folder.

```
Images/

Hardware_Setup.jpg

RFID_Scan.jpg

LCD_Output.jpg

GoogleSheet_Output.png

Arduino_SerialMonitor.png

NodeMCU_SerialMonitor.png

Circuit_Diagram.png
```

Example in Markdown:

```markdown
## Hardware Setup

![Hardware](Images/Hardware_Setup.jpg)

## LCD Output

![LCD](Images/LCD_Output.jpg)

## Google Sheet

![Google Sheet](Images/GoogleSheet_Output.png)
```

---

# ▶ Installation Guide

## Clone Repository

```bash
git clone https://github.com/yourusername/Smart-RFID-Attendance-System.git
```

---

## Arduino UNO

1. Install Arduino IDE.
2. Install the required libraries.
3. Open `RFID_Attendance.ino`.
4. Select **Arduino UNO**.
5. Upload the sketch.

---

## NodeMCU ESP8266

1. Install the ESP8266 Board Package.
2. Open `GoogleSheetsUploader.ino`.
3. Enter your Wi-Fi SSID and Password.
4. Paste your Google Apps Script Web App URL.
5. Select **NodeMCU 1.0 (ESP-12E Module)**.
6. Upload the sketch.

---

## Google Apps Script

1. Create a new Apps Script project.
2. Copy `Code.gs`.
3. Deploy as **Web App**.
4. Set access to **Anyone**.
5. Copy the deployment URL.
6. Update the URL in the NodeMCU code.

---

# ▶ Usage

1. Power the Arduino UNO.
2. Connect the NodeMCU to Wi-Fi.
3. Wait for the LCD to display **Scan Card**.
4. Scan a registered RFID card.
5. Attendance is uploaded automatically.
6. Scan the same card again to mark Logout.

---

# 📈 Project Workflow

```
Start
   │
   ▼
Scan RFID Card
   │
   ▼
Read UID
   │
   ▼
Valid Card?
 ┌───────┴────────┐
 │                │
Yes              No
 │                │
 ▼                ▼
Display Name   Access Denied
 │                │
 ▼                ▼
Green LED      Red LED
 │                │
 ▼                ▼
Send Data     End
 │
 ▼
NodeMCU
 │
 ▼
Google Apps Script
 │
 ▼
Google Sheets
 │
 ▼
Finish
```

---

# 🎯 Future Enhancements

- Face Recognition Integration
- Fingerprint Authentication
- Firebase Cloud Database
- Mobile Application
- QR Code Attendance
- Web Dashboard
- SMS Notifications
- Email Alerts
- Attendance Analytics
- Monthly Attendance Reports
- AI-based Attendance Prediction

---

# 📊 Applications

- Schools
- Colleges
- Universities
- Offices
- Libraries
- Laboratories
- Hostels
- Employee Attendance Systems

---

# ✅ Advantages

- Paperless Attendance
- Low Cost
- Easy Installation
- Cloud Storage
- Fast Authentication
- Accurate Attendance
- Scalable Design
- User Friendly

---

# 👨‍💻 Author

**Nandan Kumar M**

Bachelor of Engineering (Computer Science & Engineering)

GitHub: https://github.com/yourusername

LinkedIn: https://linkedin.com/in/yourprofile

---

# 🤝 Contributing

Contributions are welcome.

1. Fork the repository.
2. Create a feature branch.
3. Commit your changes.
4. Push to your branch.
5. Open a Pull Request.

---

# 📄 License

This project is licensed under the MIT License.

See the **LICENSE** file for details.

---

# ⭐ Support

If you found this project useful, please consider giving it a ⭐ on GitHub.

It helps others discover the project and supports future improvements.

# 🌬️ CARBON MONOXIDE ESP32 MQ7 LCD LINE NOTIFICATION

[![ESP32](https://img.shields.io/badge/Device-ESP32-red?style=for-the-badge&logo=espressif)](https://www.espressif.com/)
[![PlatformIO](https://img.shields.io/badge/IDE-PlatformIO-orange?style=for-the-badge&logo=platformio)](https://platformio.org/)
[![LINE](https://img.shields.io/badge/Notification-LINE-green?style=for-the-badge&logo=line)](https://developers.line.biz/)

## 📋 Overview

A safety-critical Carbon Monoxide (CO) detection system built with ESP32 and MQ7 sensor. This device continuously monitors CO levels, displays readings on an LCD screen, and sends immediate notifications via LINE messaging when dangerous levels are detected.

## ⚙️ Tech Stack

- **PlatformIO** - Development environment
- **Arduino Framework** - Programming framework
- **ESP32 Library** - Hardware interface library
- **MQ7 Sensor** - Carbon monoxide detection
- **LINE Notify API** - Push notifications

## 🔍 Features

- **Real-time CO Monitoring**: Continuous sampling of ambient air
- **LCD Display**: Shows current CO levels and safety status
- **Danger Threshold Alerts**: Visual warnings on dangerous CO concentrations
- **Remote Notifications**: Sends LINE messages when CO levels are unsafe
- **Portable Design**: Compact and easy to place in any room

## 📸 Project Gallery

<div align="center">
  <img src="https://github.com/user-attachments/assets/7781e571-9342-4dbb-b8a9-b846ac3d9720" width="400" alt="Complete Device Setup"/>
  <img src="https://github.com/user-attachments/assets/ca90c697-6e5a-4660-a890-dcf7f28a0789" width="400" alt="Internal Components"/>
</div>

<div align="center">
  <img src="https://github.com/user-attachments/assets/f5c29156-adbd-4f58-ba5a-356c771fb23f" width="400" alt="Display Panel View"/>
  <img src="https://github.com/user-attachments/assets/af4ec482-19bd-4279-9503-7e20ee579d37" width="400" alt="Circuit Assembly"/>
</div>

<div align="center">
  <img src="https://github.com/user-attachments/assets/2445b96b-876b-4a18-b18b-0ea2d13ccafb" width="400" alt="Testing Configuration"/>
</div>

## 🛠️ Hardware Components

- ESP32 Development Board
- MQ7 Carbon Monoxide Sensor
- 16x2 LCD Display
- Jumper Wires
- Power Supply
- Housing Case

## 📊 How It Works

1. The MQ7 sensor continuously samples air for carbon monoxide
2. ESP32 reads and processes sensor data
3. CO concentration is displayed on the LCD in real-time
4. When dangerous levels are detected:
   - LCD displays warning message
   - LINE notification is immediately sent to user
   - Visual alarm is activated

## 📝 Installation Guide

### Prerequisites

- PlatformIO IDE (or VS Code with PlatformIO extension)
- ESP32 board definition files
- LINE Notify account and token

### Setup Instructions

1. Clone this repository
2. Open project in PlatformIO
3. Install required libraries:
   - LiquidCrystal
   - ESP32 Arduino Core
   - WifiManager
   - LineNotify
4. Configure your WiFi credentials in `config.h`
5. Add your LINE Notify token in `config.h`
6. Upload sketch to your ESP32 board

## 🔧 Configuration

Key parameters can be adjusted in the `config.h` file:

```cpp
// Safety thresholds in ppm
#define CO_WARNING_LEVEL 50
#define CO_DANGER_LEVEL 100

// Notification settings
#define NOTIFICATION_COOLDOWN 300 // seconds between notifications
#define LINE_TOKEN "YOUR_LINE_TOKEN_HERE"

// Hardware pins
#define MQ7_PIN 34
#define LCD_RS 22
#define LCD_EN 23
#define LCD_D4 5
#define LCD_D5 18
#define LCD_D6 19
#define LCD_D7 21
```

## 📱 LINE Notification Setup

1. Go to [LINE Notify](https://notify-bot.line.me/)
2. Log in with your LINE account
3. Generate a new token (select a chat to send notifications to)
4. Copy the token and paste it into your `config.h` file

## ⚠️ Safety Notes

- This device is designed for early warning only and should not replace professional CO detectors
- Test the device regularly with known CO sources
- Keep the sensor clean and free from dust or contaminants
- Replace the MQ7 sensor every 2 years for best accuracy

# 🚗 IoT Car Parking Simulation using Arduino

This is a simple **Arduino-based smart parking system** that simulates how automated parking works using IR sensors, a servo motor, and an LCD display.

## 📦 Features

- Detects car entry and exit using IR sensors
- Opens and closes gate automatically with a servo motor
- Displays available parking slots on a 16x2 I2C LCD
- Shows "Parking Full" message when slots are unavailable

## 🔧 Hardware Required

- Arduino Uno
- 2x IR Sensors
- Servo Motor (SG90 or equivalent)
- 16x2 LCD with I2C module
- Jumper wires
- Breadboard

## 🧠 How It Works

- **IR1** detects an incoming car.
- **IR2** detects an exiting car.
- When a car enters and slots are available, the servo opens the gate and reduces the slot count.
- When a car exits, the slot count is increased and the gate opens.
- If the parking is full, a message is shown on the LCD and the gate stays closed.

## ⚙️ Arduino Pins Used

| Component     | Pin |
|---------------|-----|
| IR Sensor 1   | D2  |
| IR Sensor 2   | D3  |
| Servo Motor   | D4  |
| I2C LCD       | A4 (SDA), A5 (SCL) |

## 📝 Code Snippet

```cpp
int Slot = 4; // Total parking slots
```

## System Overview
          +-------------------+
IR1 ---> |   Arduino Uno      | <--- IR2
         |                   |
         |     Servo Motor   |
         |         ↓         |
         |     LCD Display   |
          +-------------------+


## 📌 Notes

- ✅ **Check the I2C Address:** Most LCDs use `0x27`, but some may use `0x3F`. Use an I2C scanner sketch to confirm.

- 🔌 **Power the Servo Properly:** The servo motor may require external 5V power for smooth operation. Powering directly from Arduino may cause jitter or failure.

- ⚠️ **Double-Check Wiring:** Incorrect connections can lead to erratic behavior or no response at all.



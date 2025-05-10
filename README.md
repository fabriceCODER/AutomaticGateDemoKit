### Automatic Gate Demo Kit ###
---

```markdown
# 🚦 Smart Gate Control System with Ultrasonic Sensor and Servo Motor

This Arduino project uses an ultrasonic sensor to detect approaching objects (e.g., people or vehicles) and automatically opens a servo-controlled gate. It features status indication with red and blue LEDs and a buzzer that beeps gently when the gate is open.

##  Features

- Automatically opens the gate when an object is within a certain distance.
- Closes the gate after 5 seconds of no detection.
- Red LED indicates gate is closed.
- Blue LED indicates gate is open.
- Buzzer provides a soft periodic beep when the gate is open.
- Reliable distance measurement using an ultrasonic sensor.

---

##  Hardware Required

| Component               | Quantity |
|------------------------|----------|
| Arduino Uno            | 1        |
| Ultrasonic Sensor (HC-SR04) | 1        |
| Servo Motor            | 1        |
| Red LED                | 1        |
| Blue LED               | 1        |
| 220Ω Resistors (for LEDs) | 2        |
| Buzzer (Active or Passive) | 1        |
| Jumper Wires           | -        |
| Breadboard             | 1        |

---

## ⚙️ Pin Configuration

| Arduino Pin | Component            |
|-------------|----------------------|
| D2          | HC-SR04 Trigger      |
| D3          | HC-SR04 Echo         |
| D4          | Red LED Anode (+)    |
| D8          | Red LED Cathode (–)  |
| D5          | Blue LED Anode (+)   |
| D7          | Blue LED Cathode (–) |
| D6          | Servo Signal         |
| D12         | Buzzer               |

---

##  How It Works

1. **Distance Measurement**  
   The ultrasonic sensor emits a sound wave and measures the time it takes to return. This time is converted into distance.

2. **Gate Control Logic**  
   - If an object is detected within **50 cm**, the servo motor rotates to open the gate (90°).
   - The blue LED turns on and a gentle beeping starts using the buzzer.
   - If no object is detected for **5 seconds**, the gate closes (servo returns to 0°), red LED turns on, and the buzzer stops.

3. **Buzzer Timing**  
   - Beeps for **50 ms** every **500 ms** while the gate is open.

---

##  Code Overview

```cpp
if (distance < thresholdDistance) {
    // Object detected: open gate, light blue LED, start beeping
} else {
    // No object: after delay, close gate, light red LED, stop beeping
}
```

- `getDistance()` handles distance reading via ultrasonic sensor.
- `myServo.write(angle)` controls gate position.
- `digitalWrite()` manages LEDs and buzzer signals.
- `millis()` handles non-blocking delays for auto-close and buzzer timing.

---

## 📦 Installation

1. Connect all components as per the pin configuration.
2. Upload the code using the Arduino IDE.
3. Power the board and observe the gate reacting to movement within range.

---

##  Troubleshooting

- **Gate not moving?** Check servo power and signal wiring.
- **No detection?** Ensure ultrasonic sensor faces the correct direction and is wired properly.
- **LEDs/Buzzer not working?** Confirm cathode/anode connections and use appropriate resistors.

---

##  Applications

- Automated entry gates
- Contactless trash bins
- Pet doors
- Interactive installations

---

## 📄 License

This project is open-source under the MIT License.

---

## 🙋‍♂️ Author

**Fabrice Ishimwe**  
Arduino Hobbyist & Embedded Systems Developer  
Contact: fabricecoder009@gmail.com

```



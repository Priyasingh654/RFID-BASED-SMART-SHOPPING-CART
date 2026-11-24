RFID-Based Human Following Trolley

📌 Project Overview

The RFID-Based Human Following Trolley is an Arduino-based smart trolley designed to make shopping more convenient and efficient. The system uses RFID technology to identify an authorized RFID tag and automatically control the movement of the trolley.

When the correct RFID tag is detected by the RC522 RFID reader, the trolley starts moving forward. When the tag is removed or an incorrect tag is detected, the trolley automatically stops.

The system also uses an HC-SR04 ultrasonic sensor to detect obstacles within a predefined distance of 20 cm. If an obstacle is detected, a buzzer turns ON to alert the user. The buzzer turns OFF when the obstacle is no longer detected.

✨ Features

- **RFID-Based Detection:** Detects the authorized RFID tag using the RC522 module.
- **Automatic Movement:** The trolley moves forward when the correct RFID tag is detected.
- **Automatic Stop:** The trolley stops when the authorized tag is not detected or an incorrect tag is presented.
- **Obstacle Detection:** HC-SR04 ultrasonic sensor detects obstacles within 20 cm.
- **Buzzer Alert:** Activates the buzzer when an obstacle is detected.
- **Arduino-Based Control:** Uses Arduino and L298N motor driver for controlling the trolley.

🛠️ Components Required

| Component | Quantity |
|---|---:|
| Arduino UNO | 1 |
| RC522 RFID Reader | 1 |
| RFID Tag/Card | 1 |
| L298N Motor Driver | 1 |
| DC Motors | 2 |
| HC-SR04 Ultrasonic Sensor | 1 |
| Buzzer | 1 |
| Battery | 1 |
| Jumper Wires | As required |
| Trolley Chassis | 1 |

🔌 Pin Connections

1. L298N Motor Driver with Arduino

| Arduino Pin | L298N Connection |
|---|---|
| D5 | Left Motor Forward |
| D6 | Left Motor Backward |
| D7 | Right Motor Forward |
| D8 | Right Motor Backward |

2. RC522 RFID Reader with Arduino

| RC522 Pin | Arduino UNO |
|---|---|
| SDA (SS) | D10 |
| SCK | D13 |
| MOSI | D11 |
| MISO | D12 |
| RST | D9 |
| 3.3V | 3.3V |
| GND | GND |

**Note:** Connect the RC522 module to 3.3V, not 5V.

3. HC-SR04 Ultrasonic Sensor

| Sensor Pin | Arduino UNO |
|---|---|
| VCC | 5V |
| GND | GND |
| TRIG | D2 |
| ECHO | D3 |

4. Buzzer

| Buzzer Pin | Arduino UNO |
|---|---|
| Positive (+) | D4 |
| Negative (-) | GND |

⚙️ Working Principle

1. The Arduino initializes the RFID reader, ultrasonic sensor, buzzer, and motor driver.
2. The RC522 RFID reader continuously checks for an RFID card.
3. When the authorized RFID tag with UID `8C 31 33 02` is detected, the Arduino activates both motors through the L298N motor driver.
4. When the RFID tag is removed or an unauthorized tag is detected, the motors stop.
5. The HC-SR04 ultrasonic sensor continuously measures the distance of nearby objects.
6. If an obstacle is detected within 20 cm, the buzzer turns ON.
7. When the obstacle is removed, the buzzer automatically turns OFF.

**Important:** Obstacle detection activates only the buzzer. It does not stop the trolley in the current program.

💻 Software Requirements

- Arduino IDE
- MFRC522 Library
- SPI Library (included with Arduino IDE)

🚀 Installation and Setup

1. Download or clone this repository.
2. Install the Arduino IDE.
3. Install the MFRC522 library from the Arduino Library Manager.
4. Connect all components according to the pin connection tables.
5. Open the Arduino source code (`.ino`) in Arduino IDE.
6. Select **Arduino UNO** as the board.
7. Select the correct COM port.
8. Upload the code to the Arduino UNO.
9. Open Serial Monitor and set the baud rate to **9600**.
10. Place the authorized RFID tag near the RC522 reader to start the trolley.

🆔 Authorized RFID Tag

The currently programmed RFID tag UID is:

`8C 31 33 02`

To use another RFID tag, update the `targetUID` array in the Arduino code.

📂 Project Structure

```text
RFID-Human-Following-Trolley/
│
├── RFID_Trolley.ino
├── README.md
└── images/
    ├── project.jpg
    └── circuit.jpg
```

🔮 Future Improvements

- Human tracking using IR or ultrasonic sensors.
- Left and right movement control.
- Improved obstacle avoidance.
- Integration with smart billing technology.
- LCD display for real-time information.
- Wireless monitoring and control.

🎯 Applications

- Smart supermarkets
- Shopping malls
- Automated shopping carts
- Assistance for elderly people
- Smart retail automation

👩‍💻 Technologies Used

- Arduino UNO
- Embedded C/C++
- RFID Technology
- Ultrasonic Sensing
- Motor Control
- Embedded Systems

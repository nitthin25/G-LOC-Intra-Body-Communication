# G-LOC-Intra-Body-Communication
ESP32-based Intra-Body Communication system for secure glucose data transmission using galvanic coupling, featuring real-time monitoring, frequency encoding/decoding, OLED visualization, and automated pump control.
# G-LOC: Glucose Level Monitoring and Control using Intra-Body Communication

## 📌 Overview

G-LOC (Glucose Level Monitoring and Control) is an ESP32-based biomedical communication system that demonstrates secure transmission of glucose-related data through the human body using **Galvanic Coupling based Intra-Body Communication (IBC)**.

The project simulates glucose levels using a potentiometer, encodes the data into a frequency signal, transmits it through the human body, decodes it at the receiver, and displays the glucose value in real time. The system also includes an automated pump control mechanism and alert buzzer for high glucose conditions.

---

## 🎯 Objectives

- Design an experimental platform for glucose-level monitoring using Intra-Body Communication.
- Implement reliable frequency-based data encoding and decoding.
- Demonstrate secure body-centric communication using galvanic coupling.
- Develop an automated decision-making system for pump actuation.
- Evaluate the feasibility of Body Area Networks (BANs) for future healthcare applications.

---

## 🚀 Key Features

- ESP32-based transmitter and receiver architecture
- Glucose level simulation using a 10kΩ potentiometer
- Frequency encoding from 100 kHz to 500 kHz
- Galvanic Coupling based Intra-Body Communication
- Real-time glucose monitoring
- OLED display visualization
- Automated pump control for high glucose levels
- Buzzer alert system
- Low-power and secure body-area communication

---

## 🧠 Working Principle

The system consists of two ESP32 modules:

### Transmitter Side
1. Reads glucose value from a potentiometer.
2. Converts the value into a frequency signal.
3. Injects the signal into the body through a transmitting electrode.

### Receiver Side
1. Receives the signal through a receiving electrode.
2. Measures the received frequency.
3. Decodes the glucose value.
4. Displays the glucose level on an OLED display.
5. Activates a pump and buzzer when glucose exceeds a predefined threshold.

---

## 📡 System Architecture

```text
Potentiometer
      │
      ▼
ESP32 Transmitter
      │
      ▼
Frequency Encoding
      │
      ▼
Human Body Channel
(Galvanic Coupling)
      │
      ▼
ESP32 Receiver
      │
      ▼
Frequency Decoding
      │
      ▼
OLED Display
      │
      ▼
Pump Control + Buzzer Alert
```

---

## 🔧 Hardware Components

### Transmitter Side

- ESP32 Development Board
- 10kΩ Potentiometer
- Stainless Steel Electrodes
- Breadboard and Jumper Wires

### Receiver Side

- ESP32 Development Board
- OLED Display (SSD1306)
- DC Water Pump
- Active Buzzer
- IRFZ44N / IRLZ44N MOSFET
- BC547 / 2N2222 NPN Transistor
- 1N4007 Flyback Diode
- 1kΩ Resistor
- 4.7kΩ / 10kΩ Resistor
- 4×AA Battery Pack
- Breadboard and Jumper Wires

---

## 🔌 Pin Configuration

### Transmitter ESP32

| ESP32 Pin | Connection |
|------------|------------|
| GPIO 4 | Potentiometer Wiper |
| GPIO 18 | Transmitting Electrode |
| 3.3V | Potentiometer VCC |
| GND | Potentiometer GND |
| GND | Ground Electrode |

---

### Receiver ESP32

| ESP32 Pin | Connection |
|------------|------------|
| GPIO 27 | Receiving Electrode |
| GPIO 32 | PCNT Control Pin |
| GPIO 21 | OLED SDA |
| GPIO 22 | OLED SCL |
| GPIO 33 | Pump Control |
| GPIO 25 | Buzzer |
| 3.3V | OLED VCC |
| GND | OLED GND |

---

## ⚙️ Pump Driver Circuit

### MOSFET Connections

| MOSFET Pin | Connection |
|------------|------------|
| Gate | GPIO 33 via 1kΩ resistor |
| Gate | GND via 10kΩ pull-down resistor |
| Drain | Pump Negative Terminal |
| Source | Common Ground |

### Diode Connections

| Diode Pin | Connection |
|-----------|------------|
| Cathode | Pump Positive Terminal |
| Anode | Pump Negative Terminal |

### Battery Connections

| Battery Terminal | Connection |
|------------------|------------|
| Positive | Pump Positive Terminal |
| Negative | Common Ground |

---

## 📊 Frequency Mapping

| Glucose Level | Frequency Range |
|---------------|----------------|
| Low | ~100 kHz |
| Normal | ~250 kHz |
| Pre-Diabetic | ~340 kHz |
| High | ~500 kHz |

---

## 📈 Sample Results

| Glucose Level | Transmitted Frequency | Received Frequency | Action |
|--------------|----------------------|--------------------|--------|
| 77 mg/dL | 154700 Hz | 154700 Hz | Pump OFF |
| 124 mg/dL | 256288 Hz | 256288 Hz | Pump OFF |
| 171 mg/dL | 342051 Hz | 342051 Hz | Pump OFF |
| 192 mg/dL | 388800 Hz | 388800 Hz | Pump ON |

---

## 🏥 Applications

- Smart Healthcare Systems
- Continuous Glucose Monitoring
- Implantable Medical Devices
- Body Area Networks (BANs)
- Secure Biomedical Communication
- Wearable Health Monitoring
- Remote Patient Monitoring

---

## 🛡️ Future Scope

- Integration with Continuous Glucose Monitors (CGM)
- Real-time insulin delivery systems
- Implantable medical devices
- Soldier Body Area Networks
- Human-Robot Interaction Systems
- Secure Authentication Systems
- Low-power wearable communication platforms

---

## 🧪 Technologies Used

- Embedded Systems
- ESP32
- Arduino IDE
- Intra-Body Communication (IBC)
- Galvanic Coupling
- Pulse Counter (PCNT)
- OLED Display Interface
- Frequency Encoding and Decoding

---

## 📷 Project Demonstration

### Prototype Images

- Transmitter Prototype
- Receiver Prototype
- OLED Output
- Serial Monitor Results

(Add images in the `images/` folder and reference them here)

---

## 📚 References

1. Maity, S., et al., "BodyWire: A 6.3-pJ/b Human Body Communication Transceiver Using Time-Domain Interference Rejection", IEEE Journal of Solid-State Circuits, 2020.
2. IEEE Transactions on Biomedical Circuits and Systems, Human Body Communication Studies (2020–2025).
3. IEEE Access, Secure Body Area Networks using Human Body Communication, 2021.
4. Sensors Journal, Galvanic Coupling Based Intra-Body Communication Systems, 2022.
5. Biomedical Signal Processing and Control, Human Body Communication for Medical Devices, 2023.
6. IEEE Internet of Things Journal, Body Area Network Applications, 2023.
7. Nature Electronics, Wearable Biomedical Communication Systems, 2024.
8. IEEE Reviews in Biomedical Engineering, Recent Advances in Intra-Body Communication, 2024.

---

## 👨‍💻 Authors

**Nitthin M M**  
B.Tech Electronics and Communication Engineering  
SRM Institute of Science and Technology

---

## 📄 License

This project is licensed under the MIT License.

---

## ⭐ Support

If you found this project interesting, consider giving the repository a ⭐ on GitHub.

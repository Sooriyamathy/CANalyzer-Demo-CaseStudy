# DBC: `vehicle.dbc` Signal Reference

---

## 📨 Messages & Signals
### Network Node Layout
![Network Node Layout](https://raw.githubusercontent.com/Sooriyamathy/CANalyzer-Demo-CaseStudy/main/Signal-Decode/flowchart.jpg)
### 1. `ABSdata` (0xC9)

| Signal        | Min | Max | Unit  | Type   | Description                |
|---------------|-----|-----|-------|--------|----------------------------|
| CarSpeed      |  0  | 300 | km/h  | Float  | Overall vehicle speed      |
| GearLock      | OFF | ON  | Bool  | UInt   | 1 if gear is locked        |
| Diagnostics   |  -  |  -  | code  | Enum   | ABS diagnostic status      |

---

### 2. `EngineData` (0x64)

| Signal        | Min | Max | Unit   | Type   | Description                      |
|---------------|-----|-----|--------|--------|----------------------------------|
| EngSpeed      |  0  | 6500| RPM    | UInt   | Engine revolutions per minute    |
| EngTemp       | -50 | 150 | °C     | Float  | Engine temperature               |
| IdleRunning   |  0  | 1   | Bool   | Bool   | 1 if engine is running           |
| PetrolLevel   |  0  | 100 | %      | Float  | Current fuel level               |

---

### 3. `EngSpeedContr` (0x12C)

| Signal  |     Min     |         Max     | Unit  | Type | Description                    |
|---------|-------------|-----------------|------|-------|--------------------------------|
| Test    |  Critical   | Not_Critical    | N/A  | TBD   | Placeholder for control test   |

---

### 4. `GearBoxInfo` (0x3FC)

| Signal        | Min | Max | Unit | Type  | Description                          |
|---------------|-----|-----|------|-------|--------------------------------------|
| Gear          |  0  | 6   | N/A  | UInt  | Gear number (0 = Neutral)            |
| ShiftRequest  |  0  | 1   | Bool | Bool  | Indicates gear shift request         |
| EcoMode       |  0  | 1   | Bool | Bool  | 1 if Eco driving mode is enabled     |

---

### 5. `WheelInfo` (0xC8)

| Signal         | Min |  Max |  Unit | Type   | Description                         |
|----------------|-----|------|-------|--------|-------------------------------------|
| WheelSpeedFL   |  0  | 1300 | 1/min | Float  | Front left wheel speed              |
| WheelSpeedFR   |  0  | 1300 | 1/min | Float  | Front right wheel speed             |
| WheelSpeedRL   |  0  | 1300 | 1/min | Float  | Rear left wheel speed               |
| WheelSpeedRR   |  0  | 1300 | 1/min | Float  | Rear right wheel speed              |

---

### 6. `WheelInfoIEEE` (0xC7)

| Signal         | Min | Max | Unit   | Type   | Description                        |
|----------------|-----|-----|--------|--------|------------------------------------|
| WheelSpeedFL   |  0  | 1300 | 1/min | Float  | IEEE version of front-left speed   |
| WheelSpeedFR   |  0  | 1300 | 1/min | Float  | IEEE version of front-right speed  |

---

## 🧩 Signal Reference List (for quick lookup)

- **Vehicle Speed**: `CarSpeed`
- **Engine RPM**: `EngSpeed`
- **Fuel**: `PetrolLevel`
- **Gear Info**: `Gear`, `ShiftRequest`, `GearLock`
- **Modes**: `IdleRunning`, `EcoMode`
- **Diagnostics**: `Diagnostics`, `Test`
- **Temperatures**: `EngTemp`
- **Wheel Speeds**: `WheelSpeedFL`, `WheelSpeedFR`, `WheelSpeedRL`, `WheelSpeedRR`

---
### 🧩 What I Learned from the Demo Mode Data
By analyzing the demo mode data for the vehicle system, I observed the interactions between various components of the vehicle, including the ABS system, engine control, gearbox information, and wheel speed data. Here’s a breakdown of key insights:

- **System Interactions**: The signals work together to manage the vehicle's performance. For example, the engine speed and gear information help determine how the vehicle accelerates or decelerates, while wheel speed data is critical for ABS and traction control systems.
- **Diagnostic Data**: The ABS system provides diagnostic codes, which are helpful for troubleshooting and maintenance. The test signals in engine control further aid in system checks.
- **Safety and Efficiency**: The vehicle’s systems are optimized for safety (through ABS and gear lock signals) and fuel efficiency (EcoMode and petrol level). The data highlights the focus on real-time adjustments based on vehicle status.

### **Conclusion**
The demo mode showcases how various vehicle components communicate in real-time to ensure optimal performance, safety, and efficiency. By observing these interactions, I gained valuable insights into vehicle system diagnostics and control mechanisms.

### 🔜 **Next Step: Signal Analysis**
In the next step, I will analyze each signal in detail to understand its role within the vehicle system and its interactions with other signals. This analysis will help uncover deeper insights into the system's performance and functionality.


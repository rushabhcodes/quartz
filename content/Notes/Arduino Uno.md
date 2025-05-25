---
created: 2025-05-25T23:45
updated: 2025-05-25T23:51
---
The **Arduino Uno** is one of the most popular microcontroller boards used in electronics, prototyping, and IoT projects. Based on the **ATmega328P microcontroller**, it is beginner-friendly, open-source, and widely supported by a large community.

---

## **1. Overview of Arduino Uno**

- **Microcontroller:** ATmega328P
    
- **Operating Voltage:** 5V
    
- **Input Voltage (recommended):** 7-12V
    
- **Clock Speed:** 16 MHz
    
- **Digital I/O Pins:** 14 (of which 6 can provide PWM output)
    
- **Analog Input Pins:** 6
    
- **Flash Memory:** 32 KB (0.5 KB used by bootloader)
    
- **SRAM:** 2 KB
    
- **EEPROM:** 1 KB
    

---

## **2. Arduino Uno Board Layout and Parts**

### **A. USB Port**

- Used to upload code from the computer to the board.
    
- Also provides power (5V) to the board during programming/testing.
    

### **B. Power Jack (Barrel Jack)**

- Allows powering the board using an external power supply (7–12V).
    

### **C. Voltage Regulator**

- Converts higher input voltage (from the power jack) down to 5V.
    

### **D. ATmega328P Microcontroller**

- The brain of the board. It executes the uploaded sketches (programs).
    

### **E. Digital I/O Pins (0–13)**

- Used for digital input/output operations.
    
- **Pins 0 (RX) and 1 (TX)** are used for serial communication.
    

### **F. PWM Pins**

- Pins **3, 5, 6, 9, 10, and 11** can output PWM signals using the `analogWrite()` function.
    

### **G. Analog Input Pins (A0–A5)**

- Used to read analog signals (0–5V), such as from sensors.
    
- Each pin has a 10-bit ADC (Analog-to-Digital Converter).
    

### **H. Power Pins**

- **Vin:** Input voltage to the Arduino board (when using external power).
    
- **5V:** Regulated 5V output (used to power sensors/modules).
    
- **3.3V:** 3.3V output (low-power modules).
    
- **GND:** Ground pins (0V reference).
    
- **AREF:** Analog Reference pin for analog inputs (optional use).
    

### **I. Reset Button**

- Resets the microcontroller, restarting the current program.
    

### **J. ICSP Header (In-Circuit Serial Programming)**

- For low-level programming of the microcontroller using an external programmer.
    

### **K. Crystal Oscillator**

- Maintains timing accuracy with a clock speed of 16 MHz.
    

### **L. TX and RX LEDs**

- Indicate data being transmitted (TX) or received (RX) via USB/serial.
    

### **M. Onboard LED (Pin 13)**

- A simple LED connected to digital pin 13 for testing.
    

---

## **3. Pin Description Summary**

|Pin Type|Pin Numbers|Function|
|---|---|---|
|Digital I/O|0–13|General-purpose digital input/output|
|PWM|3, 5, 6, 9, 10, 11|Digital pins with PWM capability|
|Analog Input|A0–A5|Read analog voltages (0–5V)|
|Power Pins|Vin, 5V, 3.3V, GND|Power inputs and outputs|
|Serial Communication|0 (RX), 1 (TX)|Receive/transmit serial data|
|SPI (via ICSP)|10 (SS), 11 (MOSI), 12 (MISO), 13 (SCK)|Serial Peripheral Interface|
|I2C|A4 (SDA), A5 (SCL)|Inter-Integrated Circuit communication|
|Reset|RESET pin/button|Resets the microcontroller|

---

## **4. Arduino Programming and IDE**

- The Arduino Uno is programmed using the **Arduino IDE** (based on C/C++).
    
- Code uploaded is called a **sketch**.
    
- Uses simple functions:
    
    - `setup()` – runs once at startup.
        
    - `loop()` – runs repeatedly after setup.
        

---

## **5. Applications of Arduino Uno**

- Sensor-based projects (temperature, motion, humidity)
    
- Home automation
    
- Robotics
    
- IoT prototypes
    
- Educational learning kits
    
- Motor control and automation
    
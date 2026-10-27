Here is a comprehensive, production-ready `README.md` for your GitHub repository based on your project source files:

```markdown
# 🏡 Bluetooth Controlled Home Automation System Using 8051

A micro-controller-based home automation project built around the **8051 architecture (AT89C51 / P89V51RD2)**[cite: 1]. This system enables wireless switching of home appliances (like lamps and fans) via an Android smartphone using **HC-05 Bluetooth module** serial communication[cite: 1].

---

## 📌 Features

* **Wireless Appliance Control:** Turn home appliances ON and OFF remotely via an Android app using Bluetooth[cite: 1].
* **Relay Isolation:** Uses a multi-channel relay module driven by a **ULN2003A** IC to safely interface low-voltage MCU digital signals with high-voltage AC electrical loads[cite: 1].
* **UART Serial Protocol:** Communicates seamlessly over RS-232 serial logic at a 9600 baud rate[cite: 1].
* **Instant Feedback:** Sends real-time status strings (e.g., `Lamp_ON`, `Fan_OFF`) back to the connected Bluetooth terminal app[cite: 1].

---

## 📐 Block Diagram & System Architecture


```

+------------------+         +--------------------+         +---------------+         +--------------+
| Android Phone    | Bluetooth| HC-05 Module       | Serial  | 8051 Micro    | Digital | Relay Driver |
| (App Controller) |-------->|(RX/TX @ 9600 Baud) |-------->| (AT89C51)     |-------->| (ULN2003A &  |
+------------------+         +--------------------+ (P3.0/1)|               | (Port 2)| Relays)      |
+----------------+         +-------+------+
|
+------+------+
| AC Loads    |
| (Fan, Light)|
+-------------+

```

---

## 🛠️ Hardware Components

| Component | Description / Part Number |
| :--- | :--- |
| **Microcontroller** | 8051 Family (AT89C51 / P89V51RD2 / PS-8051-EVB-V4 Board)[cite: 1] |
| **Bluetooth Module** | HC-05 Serial Module (IEEE 802.15.1)[cite: 1] |
| **Relay Driver** | ULN2003A Darlington Transistor Array[cite: 1] |
| **Relays** | 5V DC Relays (AC load switching)[cite: 1] |
| **Power Supply** | 12V DC input with LM7805 Voltage Regulator (5V output)[cite: 1] |
| **Crystal Oscillator** | 11.0592 MHz (Standard UART baud rate generation)[cite: 1] |
| **Loads** | AC Fan, Lamp / Bulb[cite: 1] |

---

## 💻 Software & Tools

* **Keil µVision C51:** Embedded C IDE and compiler[cite: 1].
* **Nuvoton / Flash Magic ISP Utility:** ISP hex flashing tool[cite: 1].
* **HyperTerminal / Serial Monitor:** Testing UART serial communication[cite: 1].
* **Android Bluetooth Terminal App:** Available on Google Play Store[cite: 1].

---

## 📶 HC-05 Bluetooth Module Configuration

* **Default Bluetooth Name:** `HC-05`[cite: 1]
* **Default Passkey/PIN:** `1234` or `0000`[cite: 1]
* **Baud Rate (Data Mode):** `9600, 8, N, 1`[cite: 1]
* **Command Mode Baud Rate:** `38400, 8, N, 1`[cite: 1]
* **Operating Mode:** Slave Mode[cite: 1]

---

## 🔄 Command Control Protocol

| Received Character | Microcontroller Action | Pin Output State | Response String Sent |
| :---: | :--- | :---: | :---: |
| `'1'` | Turn Lamp ON | `P2^0 = 1` | `"Lamp_ON"` |
| `'2'` | Turn Lamp OFF | `P2^0 = 0` | `"Lamp_OFF"` |
| `'3'` | Turn Fan ON | `P2^1 = 1` | `"Fan_ON"` |
| `'4'` | Turn Fan OFF | `P2^1 = 0` | `"Fan_OFF"` |

---

## ⚡ Circuit Connections

1. **Bluetooth HC-05 Module:**
   * `TXD` $\rightarrow$ 8051 `P3.0` (RXD)[cite: 1]
   * `RXD` $\rightarrow$ 8051 `P3.1` (TXD)[cite: 1]
   * `VCC` $\rightarrow$ `+5V`
   * `GND` $\rightarrow$ `GND`
2. **Relay Driver (ULN2003A & Relays):**
   * Inputs $\rightarrow$ 8051 `P2.0` (Lamp) & `P2.1` (Fan)[cite: 1]
   * Outputs $\rightarrow$ Relay Coil Terminals[cite: 1]
   * Relay Contacts $\rightarrow$ Connected in series with 220V AC Power source and appliances[cite: 1]

---

## 📁 Repository Structure


```

├── HOME/
│   ├── HOME.c                 # Main Embedded C Source Code
│   ├── HOME.uvproj            # Keil µVision Project File
│   ├── HOME.uvopt             # Keil Project Options
│   ├── Objects/
│   │   ├── HOME.hex           # Compiled Binary Executable Hex File
│   │   └── HOME.obj           # Object File
│   └── Listings/
│       ├── HOME.m51           # Linker Map File
│       └── HOME.lst           # Compiler Listing File
└── README.md                  # Documentation File

```

---

## 🚀 How to Build & Run

1. **Compile Code:**
   * Open `HOME/HOME.uvproj` using **Keil µVision**[cite: 1].
   * Build the project (`F7`) to output the `HOME.hex` file located in the `Objects/` folder[cite: 1].
2. **Burn Hex File:**
   * Connect your 8051 development board to your PC via USB-to-UART / Serial connector[cite: 1].
   * Open your ISP Flashing Utility (e.g., Nuvoton ISP / Flash Magic) and flash `HOME.hex` into microcontroller memory[cite: 1].
3. **Hardware Setup:**
   * Connect the HC-05 Bluetooth module and relay circuits according to the schematic[cite: 1].
   * Power on the 8051 board[cite: 1].
4. **App Connection:**
   * Enable Bluetooth on your Android phone and pair with **HC-05** using PIN `1234` or `0000`[cite: 1].
   * Open any Bluetooth Terminal app from the Google Play Store, connect to `HC-05`, and send commands `1`, `2`, `3`, or `4`[cite: 1].

---

## 📜 License
This project is open-source and free to use under the MIT License.

```

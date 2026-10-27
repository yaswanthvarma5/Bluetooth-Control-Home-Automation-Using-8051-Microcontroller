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

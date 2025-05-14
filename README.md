# FPGA-Based Biometric Fingerprint Detection System

This project implements a **UART-based fingerprint detection and recognition system on FPGA** using Verilog HDL. It simulates a basic biometric memory-matching process where received fingerprint data is checked against a predefined ROM. The system is designed for academic exploration of biometric security and embedded UART communication in digital systems.

---

## 📦 Project Summary

- **Title**: Fingerprint Detection using FPGA
- **Platform**: FPGA (DE2 Board)
- **Language**: Verilog HDL
- **Authors**: Neha Golani (22BEC042), Ditsa Patel (22BEC036)
- **Guide**: Prof. Hardik Joshi, Prof. Mihir Shah
- **Institution**: Nirma University
- **Submitted**: November 2023

---

## 🔧 Modules Overview

### ✅ `fpga_biometric_system`
A UART receiver module that:
- Detects and verifies start, data, and stop bits
- Receives 8-bit serial data from the fingerprint sensor or simulator
- Signals data validity (`o_Rx_DV`) and outputs the received byte (`o_Rx_Byte`)

### ✅ `memory`
A simplified biometric database:
- Stores up to 3 unique 8-bit fingerprint entries
- Compares incoming byte with stored patterns
- Flags whether the fingerprint is already present (`d_check`)
- Stores new fingerprints if space is available (`d_store`)

---

## ⚙️ Features

- 📥 **UART Receiver**: Implements standard serial communication protocol
- 🔐 **Biometric Match**: Validates received data against stored entries
- 🧠 **Memory Logic**: Dynamically stores up to 3 new valid fingerprints
- 🧪 **Simulation Friendly**: Verilog structured for testing waveform accuracy

---

## 📈 System Flow

1. Receive serial fingerprint data via UART
2. Compare against 3-slot ROM
3. If matched → `d_check = 1`
4. If unmatched and space available → store new fingerprint and set `d_store = 1`
5. If no space → no update, data discarded

---

## 🧪 Testing & Output

- Verified using ModelSim simulation
- RTL viewer and waveforms match expected UART protocol
- Output flags (`d_check`, `d_store`) confirm match/miss states


---

## 🔮 Future Enhancements

- Add fingerprint sensor integration (e.g., R307 module)
- Expand memory array for larger databases
- Add interface for real-time enrollment/deletion
- Integrate secure storage with encryption
- Add machine learning for smart biometric classification

---

## 📚 References

- DE2 FPGA Board Documentation
- R307 Fingerprint Sensor Datasheet
- [FSM - Wikipedia](https://en.wikipedia.org/wiki/Finite-state_machine)
- [UART - Wikipedia](https://en.wikipedia.org/wiki/Universal_asynchronous_receiver-transmitter)

---

## 📄 License

This project is licensed under the [MIT License].


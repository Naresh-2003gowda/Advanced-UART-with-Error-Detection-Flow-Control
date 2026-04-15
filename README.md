# 🚀 Advanced-UART-with-Error-Detection-Flow-Control (Verilog)

# 📌 Overview

This project implements an Advanced UART (Universal Asynchronous Receiver Transmitter) in Verilog with enhanced reliability features including error detection and flow control. The design ensures accurate and robust serial communication, validated through simulation.

# 🎯 Key Features
✅ UART Transmitter and Receiver (TX/RX)
✅ Mid-bit sampling for accurate data reception
✅ Framing error detection (stop-bit validation)
✅ Scalable architecture for parity integration
✅ Self-checking testbench for automated verification
✅ Reliable data transmission across multiple patterns
✅ Zero packet loss observed in simulation

# 🧠 Design Details

🔹 Transmitter (TX)
- Generates UART frame:
- Start bit (0)
- 8 data bits (LSB first)
- Stop bit (1)
- Baud rate controlled using clock divider
- Serializes parallel input data
🔹 Receiver (RX)
- Detects start bit and aligns sampling
- Uses mid-bit sampling for accurate data capture
- Reconstructs serial data into parallel output
- Validates stop bit to detect framing errors
- Generates data_valid signal upon successful reception
🔹 Top Module
- Connects TX and RX internally (loopback)
- Enables end-to-end communication verification

# 🧪 Testbench Features

🔹Self-checking testbench (automatic PASS/FAIL)
🔹Event-driven verification using data_valid
🔹Multiple test cases:
🔹0xA5, 0x3C, 0x00, 0xFF
🔹Waveform generation using VCD dump
🔹Simulation-based validation of full data path

# 📊 Simulation Results

- PASS: Sent A5, Received A5
- PASS: Sent 3C, Received 3C
- PASS: Sent 00, Received 00
- PASS: Sent FF, Received FF

✔ Verified correct transmission and reception
✔ No data corruption observed
✔ Stable operation across all test cases

# 🛠️ Tools & Technologies

🔹Verilog HDL
🔹EDA Playground
🔹ModelSim / Icarus Verilog
🔹GTKWave (Waveform Viewer)

# 📂 Project Structure

├── design.sv        # UART TX, RX, Top module
├── testbench.sv     # Self-checking testbench
├── dump.vcd         # Waveform output (generated)
└── README.md

# 🚀 How to Run

▶ Using Icarus Verilog
- iverilog -g2012 design.sv testbench.sv
- vvp a.out
- gtkwave dump.vcd
▶ Using EDA Playground
- Upload design.sv and testbench.sv
- Select Icarus Verilog / ModelSim
- Run simulation
- Open waveform viewer

# 📈 Future Improvements

🔹 Parity bit generation and checking
🔹 Full error detection (parity + framing flags)
🔹 FIFO buffer for high-speed data handling
🔹 Hardware flow control (RTS/CTS)
🔹 Configurable baud rate

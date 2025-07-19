# STM32
# Tutorial6 STM32 UART Rx Interrupt Command Parser

This project demonstrates how to use **UART receive interrupts** on an STM32 microcontroller to build a simple **command parser**. When a user types a message (like `hello`) in a serial terminal and presses Enter, the STM32 receives and processes the command, and responds accordingly.

---

## 🚀 Project Overview

- MCU: STM32F4 Series (e.g., STM32F401RE)
- Toolchain: STM32CubeIDE
- UART: USART2
- Communication: UART Rx using Interrupts
- Terminal: PuTTY / Tera Term / Serial Monitor
- Baudrate: 115200

---

## 🛠️ Features

- Interrupt-based UART reception (byte-by-byte)
- String command matching (e.g., `hello`)
- Sends different responses for valid/invalid commands
- Clears buffers and listens continuously

---

## 🧠 How It Works

1. UART is configured in interrupt mode to receive one character at a time.
2. Each character is added to a buffer until the **Enter key** (`'\r'`) is received.
3. When Enter is detected:
    - If buffer matches `"hello"` → responds with `"Hello to you too\n"`
    - Otherwise → responds with `"Uh oh, something didn’t work...\n"`
4. Buffers are cleared and UART interrupt is re-armed for the next message.

---

## 💻 How to Use

1. Clone/download this repository.
2. Open the project with **STM32CubeIDE**.
3. Connect your Nucleo board via USB.
4. Open **STM32CubeProgrammer** to find the COM port.
5. Open **PuTTY** or another terminal:
   - Baud: 115200
   - Data Bits: 8
   - Parity: None
   - Stop Bits: 1
   - COM Port: e.g., `COM13`
6. Type a command (e.g., `hello`) and press **Enter**.
7. See the response printed from STM32.

---

## 🧾 Example Terminal Output


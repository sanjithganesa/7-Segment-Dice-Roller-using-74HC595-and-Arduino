# 🎲 7-Segment Dice Roller using 74HC595 and Arduino (or ATtiny)

## 📌 Objective
This project demonstrates how to use a **74HC595 shift register** to control a **common cathode (CC) 7-segment display** with a microcontroller (Arduino or ATtiny). It simulates a **dice roll** when a button is pressed, randomly displaying values between **1 and 6** on the 7-segment display.

---

## 🛠️ Components Required

| Name     | Quantity | Component                        |
|----------|----------|----------------------------------|
| Digit1   | 1        | Cathode 7-Segment Display        |
| U1       | 1        | 8-Bit Shift Register (74HC595)   |
| U2       | 1        | ATtiny (or Arduino alternative)  |
| S1       | 1        | Pushbutton                       |
| R1       | 1        | 10 kΩ Resistor                   |
| R2       | 1        | 330 Ω Resistor                   |
| P1       | 1        | 6V / 5V Power Supply             |

---

## 🔧 Working Principle

1. **Shift Register Control**  
   The **74HC595** shift register allows control of the 7-segment display using only 3 digital pins (data, clock, latch), reducing pin usage on the microcontroller.

2. **Dice Simulation**  
   - On button press, a **random number (1–6)** is generated using a custom function `RND()`.
   - A **rolling animation** is shown using the `rollDice()` function to mimic a real dice roll.
   - The final number is then displayed.

3. **Display Logic**  
   - Each digit is represented by a byte pattern for segment activation.
   - Compatible with **common cathode** (default) or **common anode** displays (toggle using `#define segDISPLAY`).

---

## ⚙️ Code Highlights

- `digit[]` – Stores the binary patterns for digits 0–6, OFF, and 8.
- `LEDwrite(int)` – Sends digit pattern to 74HC595 and updates the 7-segment display.
- `RND()` – Generates a pseudo-random number between 1 and 6 using analog noise.
- `rollDice(times)` – Runs an animation cycling through numbers 1 to 6 forward and backward.
- `loop()` – Detects button press and triggers dice roll and display.

---


# 🎲 7-Segment Dice Roller using 74HC595 and Arduino

## 📌 Objective
This project demonstrates how to use a **74HC595 shift register** to control a **common cathode (CC) or common anode (CA) 7-segment display** with an Arduino. It simulates a **dice roll** when a button is pressed, randomly displaying values between **1 and 6** on the 7-segment display.

---

## 🛠️ Components Used
- Arduino (e.g., Uno, Nano)
- 74HC595 shift register
- Common cathode/anode 7-segment display
- Push button
- Resistors (for display and button)
- Breadboard and jumper wires

---

## 🔧 Working Principle

1. **Shift Register Control**  
   The **74HC595** shift register allows control of the 7-segment display using only 3 digital pins (data, clock, latch), reducing pin usage on the Arduino.

2. **Dice Simulation**  
   - On button press, a **random number (1–6)** is generated using a custom function `RND()`.
   - A **rolling animation** is shown using the `rollDice()` function to mimic a real dice roll.
   - The final number is then displayed.

3. **Display Logic**  
   - Each digit is represented by a byte pattern for segment activation.
   - Compatible with **common cathode (default)** or **common anode** displays (toggle using `#define segDISPLAY`).

---

## ⚙️ Code Highlights

- `digit[]` – Stores the binary patterns for digits 0–6, OFF, and 8.
- `LEDwrite(int)` – Sends digit pattern to 74HC595 and updates the 7-segment display.
- `RND()` – Generates a pseudo-random number between 1 and 6 using analog noise.
- `rollDice(times)` – Runs an animation cycling through numbers 1 to 6 forward and backward.
- `loop()` – Detects button press and triggers dice roll and display.

---

## 📈 Possible Enhancements

- Add sound effects using a buzzer during the roll animation.
- Improve randomness by using better entropy sources.
- Expand to dual dice display using a second 7-segment and chained 74HC595.

---

## 📷 Demo Preview

> *(Include an image or GIF here if available)*

---

## 💡 Notes

- Default configuration is for **common cathode** displays.
- To switch to **common anode**, remove or comment the line:
  ```cpp
  #define segDISPLAY CATHODE


PROTO2 -> Project with Digilab

# Simon Says - Digital Logic Puzzle Game

A memory-based logic puzzle game built using a **Raspberry Pi**, **Node-RED** and a **Digilab** with LEDs, buttons, an LCD, and an RGB LED.

This project recreates the classic **Simon Says** game, where a sequence of lights is displayed and the player must repeat the pattern by pressing buttons in the correct order. With each success, the sequence grows harder!

![Simon Says Hardware Setup](images/SimonGame.png)

---

## Features

- LED-based visual sequence
- Button-based user input
- LCD display for messages and level info
- RGB LED for feedback (green = correct, red = wrong)
- Game logic handled in Node-RED
- Node-RED Dashboard for game control and status

---

## Hardware Requirements

- Raspberry Pi 
- Digilab with:
  - 4 Buttons
  - 4 LEDs
  - RGB LED
  - LCD Display
- Jumper wires & resistors

---

## Wiring Overview

| Component | Raspberry Pi GPIO Example |
|----------|----------------------------|
| Button 1 | GPIO 5                     |
| Button 2 | GPIO 6                     |
| Button 3 | GPIO 13                    |
| Button 4 | GPIO 19                    |
| LED 1    | GPIO 17                    |
| LED 2    | GPIO 18                    |
| LED 3    | GPIO 27                    |
| LED 4    | GPIO 22                    |
| RGB LED  | GPIO 20 (R), 21 (G), 26 (B)|
| LCD (I²C)| SDA/SCL                    |
| GND      | All components grounded    |

---

## Game Logic

1. Press "Start" on the Node-RED dashboard or a physical button.
2. A random LED flashes – that's the first step.
3. Player must press the matching button.
4. If correct:
   - A new LED is added to the sequence.
   - LCD displays new level.
5. If incorrect:
   - RGB flashes red.
   - LCD shows “Wrong! Try Again.”

---

## 🖥️ Node-RED Dashboard

- **Start Game** button
- **Current Level** display
- **Game Status** (e.g., "Correct!", "Wrong!")
- (Optional) Score graph and high score tracker

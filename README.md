# Stepper Motor Speed Control with PIC16F877A

This project implements a speed control system for a unipolar stepper motor using a PIC16F877A microcontroller. The speed is selected via two DIP switches, and the current speed level (1, 2, or 3) is displayed on a 7‑segment display. Timer0 generates precise, non‑blocking delays by polling the T0IF flag.

## Features

- **Microcontroller:** PIC16F877A @ 4 MHz  
- **Language:** Assembly (MPLAB)  
- **Inputs:** RA0, RA1 with pull‑down resistors  
- **Outputs:**  
  - RB0–RB3 → Stepper motor coils (wave drive sequence)  
  - PORTD → Common‑cathode 7‑segment display (with current‑limiting resistors)  
- **Speeds:**  
  - Slow (65 ms/step)  
  - Medium (33 ms/step)  
  - Fast (12 ms/step)  
- **Timing:** Timer0 with 1:256 prescaler, non‑blocking polling

## Schematic

<img width="1176" height="749" alt="image" src="https://github.com/user-attachments/assets/befb213e-3920-4855-ac65-560ad7fce5ed" />


## Bill of Materials

| Component                     | Quantity |
|-------------------------------|----------|
| PIC16F877A                    | 1        |
| 4 MHz crystal                 | 1        |
| 22 pF capacitors              | 2        |
| Unipolar stepper motor        | 1        |
| Common‑cathode 7‑segment display | 1     |
| NPN transistors (e.g., 2N2222)| 4        |
| 330 Ω resistors               | 7        |
| 10 kΩ pull‑down resistors     | 2        |
| 5 V (logic) + 12 V (motor) power supply | |
| Breadboard and jumper wires   |          |

## Usage

1. Assemble the circuit as shown in the schematic.  
2. Program the PIC16F877A with the provided `.hex` file (use a programmer like PICkit).  
3. Apply 5 V to the microcontroller and 12 V to the motor.  
4. Set the DIP switches to select the speed:  
   - `00` or `11` → Slow (1)  
   - `10` → Medium (2)  
   - `01` → Fast (3)  
5. The 7‑segment display shows the selected speed, and the motor rotates continuously at that speed.

## Credits

**Authors:** Juan Pablo González, Samuel David Martínez  
**Course:** Digital Systems – Microcontroller and Laboratory  
**Professor:** Marcos R. Gómez Sierra  
**Institution:** Universidad Pontificia Bolivariana – Montería Section


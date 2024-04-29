# Keypad_Passcode_LCD

# ESP32 Keypad and LCD Passcode Lock README

This project implements a passcode lock system using a keypad for input and an I2C-based LCD for displaying messages and the passcode input. Users can enter a passcode using the keypad, and the system will compare it against a predefined passcode. If the entered passcode matches the predefined one, a success message is displayed, and a welcome tone is played. Otherwise, an error message is displayed, and the system notifies the user with a buzzer sound.

## Components Used
- ESP32 Development Board
- 4x4 Matrix Keypad
- I2C-based 16x2 LCD Display
- Buzzer
- Jumper wires

## Pinout and Connections
- Keypad Connections:
  - Row 1: GPIO13
  - Row 2: GPIO14
  - Row 3: GPIO27
  - Row 4: GPIO26
  - Column 1: GPIO25
  - Column 2: GPIO33
  - Column 3: GPIO32
  - Column 4: GPIO5

- LCD Connections:
  - SDA: GPIO21
  - SCL: GPIO22
  - VCC: 5V
  - GND: GND

- Buzzer Connection:
  - Signal: GPIO2

## Setup
1. Connect the keypad and LCD to the ESP32 development board according to the pinout described above.
2. Upload the provided Arduino sketch to the ESP32 board using the Arduino IDE or another compatible development environment.
3. Open the serial monitor to view debug messages (optional).

## Operation
1. Upon powering on the system, the LCD will display "Enter Passcode:" prompting the user to enter the passcode.
2. Use the keypad to enter the passcode. Press '*' to erase the last entered digit.
3. Press '#' to submit the entered passcode.
4. If the entered passcode matches the predefined one, the LCD will display "Passcode correct!" and play a welcome tone.
5. If the entered passcode is incorrect, the LCD will display "Passcode incorrect!" and emit a buzzer sound.
6. After 2 seconds, the LCD will clear and display "Enter Passcode:" again, ready for the next input.

## Notes
- The passcode is predefined in the Arduino sketch and can be modified as needed.
- Adjust the LCD address in the sketch if your LCD has a different address (0x27 is commonly used).
- Customize the welcome tone by changing the frequency and duration in the `playWelcomeTone()` function.

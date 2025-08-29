# WORKSHOP-1
# Aim
To design and simulate a binary counter circuit that increments or decrements the count using a switch, displaying the output on a seven-segment display interfaced with Arduino Uno.

# Components Required
Arduino Uno
1x Seven-segment LED display (Common Cathode or Anode, specify in circuit)
Ground
Proteus software (for simulation purposes)

# Component Overview
## Arduino Uno
Arduino Uno is a popular microcontroller development board based on ATMega328P. It provides digital I/O pins for interfacing with external devices such as displays and switches.

## Seven Segment Display
A seven segment display consists of seven LEDs arranged in a figure of eight pattern. Each segment is labeled a-g and can be individually controlled to display digits 0-9 (and sometimes A-F). Common Anode or Common Cathode type determines wiring, with common anode connected to 5V (segments turned on by grounding corresponding pins), or common cathode connected to GND (segments turned on by supplying HIGH voltage).
# Diagram 
<img width="811" height="610" alt="Screenshot 2025-08-29 103357" src="https://github.com/user-attachments/assets/a72ff87f-5896-4250-aab2-24687cab4db9" />

# Program
```
int a = 2;
int b = 3;
int c = 4;
int d = 5;
int e = 6;
int f = 7;
int g = 8;

void setup() {
  pinMode(a, OUTPUT);
  pinMode(b, OUTPUT);
  pinMode(c, OUTPUT);
  pinMode(d, OUTPUT);
  pinMode(e, OUTPUT);
  pinMode(f, OUTPUT);
  pinMode(g, OUTPUT);
}

void loop() {
  // Display "6" → Segments ON = a, f, e, d, c, g
  digitalWrite(a, HIGH);
  digitalWrite(b, LOW);
  digitalWrite(c, HIGH);
  digitalWrite(d, HIGH);
  digitalWrite(e, HIGH);
  digitalWrite(f, HIGH);
  digitalWrite(g, HIGH);
}
```
<img width="1919" height="1079" alt="Screenshot 2025-08-29 102015" src="https://github.com/user-attachments/assets/af80221c-6637-41a4-8fa2-802d726709ad" />

# Output
<img width="1919" height="1079" alt="Screenshot 2025-08-29 102029" src="https://github.com/user-attachments/assets/53b11d25-01d1-4431-b94e-d61fd70b0900" />


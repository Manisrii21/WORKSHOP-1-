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
<img width="1191" height="821" alt="Screenshot 2025-08-29 105655" src="https://github.com/user-attachments/assets/31192933-9777-4fee-b503-855437e44f10" />

# Program
```
int segPins[] = {13,12,11,10,9,8,7}; 
int buttonPin = 2;
int count = 0;
bool lastButtonState = HIGH;
byte digits[10][7] = {
  {1,1,1,1,1,1,0}, 
  {0,1,1,0,0,0,0}, 
  {1,1,0,1,1,0,1}, 
  {1,1,1,1,0,0,1}, 
  {0,1,1,0,0,1,1}, 
  {1,0,1,1,0,1,1}, 
  {1,0,1,1,1,1,1}, 
  {1,1,1,0,0,0,0}, 
  {1,1,1,1,1,1,1}, 
  {1,1,1,1,0,1,1}  
};

void setup() {
  for(int i=0; i<7; i++) {
    pinMode(segPins[i], OUTPUT);
  }
  pinMode(buttonPin, INPUT_PULLUP); 
  displayDigit(count);
}

void loop() {
  bool buttonState = digitalRead(buttonPin);

  if (lastButtonState == HIGH && buttonState == LOW) {
    count++;
    if (count > 9) count = 0;
    displayDigit(count);
    delay(200); // debounce
  }
  lastButtonState = buttonState;
}

void displayDigit(int num) {
  for (int i=0; i<7; i++) {
    digitalWrite(segPins[i], digits[num][i]);
    }
}
```
<img width="1919" height="1078" alt="Screenshot 2025-08-29 105425" src="https://github.com/user-attachments/assets/96177f76-9dcb-42db-8934-42ead0be4f75" />

# Output
<img width="1919" height="1079" alt="Screenshot 2025-08-29 105414" src="https://github.com/user-attachments/assets/09610f8d-44fb-44b5-aac8-20764fa19163" />
<img width="1919" height="1078" alt="Screenshot 2025-08-29 105401" src="https://github.com/user-attachments/assets/783daade-1e42-4839-a0f7-ffda360a797b" />


# Arduino Projects

A collection of Arduino sketches based on the official Arduino Starter Kit. Each project explores core electronics and programming concepts — digital/analog I/O, PWM, servo control, tone generation, motor control, LCD displays, and more.

Several projects include an `-expanded` variant that extends the base circuit with additional components or behavior.

---

## Projects

### Love-O-Meter
**Folder:** `love_o_meter/`

Reads temperature from a TMP36 sensor and lights up LEDs based on how far the temperature is above a 22 °C baseline. Each additional 2 °C lights another LED (3 LEDs total on pins 2–4).

**Expanded (`love_o_meter-expanded/`):** Adds a second TMP36 on A1 and a fourth LED (pin 5) that illuminates when both sensors read the same value.

**Components:** TMP36 temperature sensor, 3–4 LEDs

---

### Spaceship Interface
**Folder:** `spaceship_interface/`

A pushbutton (pin 2) controls three LEDs (pins 3–5). While the button is unpressed all three LEDs stay on; pressing it triggers a timed blink sequence.

**Expanded (`spaceship_interface-expanded/`):** Extends to four LEDs (pins 3–6) with a more elaborate alternating blink sequence for each switch state.

**Components:** Pushbutton, 3–4 LEDs

---

### Mood Cue
**Folder:** `mood_cue/`

Maps a potentiometer reading (0–1023) to a servo angle (0–179°) via the `Servo` library, giving physical feedback as the knob turns.

**Expanded (`mood_cue-expanded/`):** Functionally identical but uses a generic sensor pin label, making it easy to swap the pot for another analog sensor.

**Components:** Potentiometer, servo motor

---

### Keyboard Instrument
**Folder:** `keyboard_instrument/`

Reads four buttons wired as a resistor ladder on A0. Each button produces a distinct analog voltage that maps to a musical note — C4 (262 Hz), D4 (294 Hz), E4 (330 Hz), F4 (349 Hz) — played through a piezo buzzer on pin 8.

**Components:** 4 pushbuttons, resistor ladder, piezo buzzer

---

### Light Theremin
**Folder:** `light_theremin/`

Calibrates a photoresistor over 5 seconds at startup (an LED on pin 23 stays on during calibration), then continuously maps the live light level to a pitch between 50 Hz and 4000 Hz played on pin 8.

**Components:** Photoresistor, piezo buzzer, LED

---

### Digital Hourglass
**Folder:** `digital_hourglass/`

Six LEDs on pins 2–7 act as a countdown timer. One LED turns on every 6 seconds. A tilt switch (pin 8) resets the hourglass when its state changes.

**Expanded (`digital_hourglass-expanded/`):** When all six LEDs are lit the entire bar flashes on/off continuously until the hourglass is reset.

**Components:** 6 LEDs, tilt switch

---

### Color Mixing Lamp
**Folder:** `color_mixing_lamp/`

Three potentiometers on A0, A1, and A2 independently control the red, green, and blue channels of an RGB LED (pins 10, 9, 11). Sensor values (0–1023) are scaled to PWM range (0–255) by dividing by 4.

**Components:** RGB LED, 3 potentiometers

---

### Motorized Pinwheel
**Folder:** `motorized_pinwheel/`

A pushbutton (pin 2) switches a DC motor (pin 9) on and off.

**Expanded (`motorized_pinwheel-expanded/`):** Adds a potentiometer on A0 to control motor speed via PWM (`analogWrite`), with speed values printed over Serial.

**Components:** DC motor, pushbutton, potentiometer (expanded only)

---

### Zoetrope
**Folder:** `zoetrope/`

Full bidirectional DC motor control via an L293D H-bridge driver. A toggle switch (pin 5) enables/disables the motor, a second switch (pin 4) reverses direction, and a potentiometer (A0) sets speed. Control signals go to pins 2 and 3; the enable/PWM line is pin 9.

**Components:** DC motor, L293D H-bridge, 2 pushbuttons, potentiometer

---

### Crystal Ball
**Folder:** `crystal_ball/`

Uses the `LiquidCrystal` library to drive a 16×2 LCD. Pressing a button (pin 6) picks one of eight random responses (*Yes*, *Most Likely*, *Certainly*, *Outlook Good*, *Unsure*, *Ask Again*, *Doubtful*, *No*) and displays it on the screen.

**Components:** 16×2 LCD display, pushbutton

---

## Libraries Used

| Library | Used by |
|---|---|
| `Servo` | mood_cue |
| `LiquidCrystal` | crystal_ball |

All other projects use only built-in Arduino functions.

---

## Getting Started

1. Open any `.ino` file in the [Arduino IDE](https://www.arduino.cc/en/software).
2. Select your board and port under **Tools**.
3. Click **Upload**.

Wire each circuit according to the pin assignments described above or in the corresponding project's sketch comments.

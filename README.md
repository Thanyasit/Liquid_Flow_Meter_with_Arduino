# Liquid Flow Meter with Arduino
<h2>Description</h2>
This code is for an Arduino-based liquid flow meter using a hall-effect sensor. The flow meter is designed to measure the rate of liquid flow and display it on a Liquid Crystal Display (LCD) in liters per hour. The flow meter has a setpoint feature that allows the user to set a desired flow rate, and the meter will turn a digital output on or off based on whether the measured flow rate is above or below the setpoint.<br>
<b>2023</b>
<h2>Hardware Requirements</h2>

- Arduino board<br>
- Hall-effect sensor (connected to digital pin 2)<br>
- 16x2 LCD display (connected via I2C to pins A4 and A5)<br>
- 2 push buttons (connected to digital pins 4 and 5)<br>
- 1 LED (connected to digital pin 6)<br>
<h2>Prerequisites</h2>

- Wire.h: Enables communication with I2C devices.<br>
- LiquidCrystal_I2C.h: Provides an interface to LCD displays that use the I2C bus.<br>
<h2>Code Overview</h2>

- <b>'NbTopsFan'</b> and <b>'Calc'</b> are integer variables used to count the number of pulses from the hall-effect sensor and calculate the flow rate.
- The <b>'rpm'()</b> function is called by an interrupt whenever a pulse is detected from the hall-effect sensor. It increments <b>NbTopsFan</b> each time it is called.
- The <b>'setup'()</b> function initializes the pins, the LCD display, and sets the initial values of the variables.
- The <b>'loop()'</b> function reads the setpoint value from the push buttons, turns the LED on or off depending on whether the flow rate is above or below the setpoint, and updates the LCD display with the current flow rate and setpoint values.
- The flow rate is calculated by dividing the number of pulses (<b>'NbTopsFan'</b>) by a conversion factor of 7.5Q. The result is then multiplied by 60 to convert the flow rate from pulses per second to liters per hour. The result is stored in Calc.
- The <b>'delay()'</b> function is used to wait for a short period between iterations of the <b>'loop()'</b> function.
<h2>Usage</h2>
Connect the hardware components as described above and upload the code to the Arduino board. Adjust the setpoint value using the push buttons. The LED will turn on or off depending on whether the measured flow rate is above or below the setpoint, and the LCD display will show the current flow rate in liters per hour and the setpoint value.

<p align="center">
<img src="https://user-images.githubusercontent.com/77733903/226800543-61ceb1f3-acbc-4923-951a-6eef3c92322e.jpg" width="500">
</p>
<p align="center">
<img src="https://user-images.githubusercontent.com/77733903/226800548-7f3613d3-3dd7-40c9-8a3b-49489d228c34.jpg" width="500">
</p>

<h2>License</h2>

This code is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

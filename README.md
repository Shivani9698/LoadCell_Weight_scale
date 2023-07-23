# HX711 Load Cell Amplifier Arduino Sketch

This repository contains an Arduino sketch that demonstrates how to interface with the HX711 load cell amplifier to read weight measurements from a load cell. The sketch uses the HX711 library to perform calibration, tare, and get weight readings.

## Hardware Requirements

To use this Arduino sketch, you will need the following components:

1. Arduino board (e.g., Arduino Uno)
2. HX711 load cell amplifier module
3. Load cell with appropriate capacity and specifications
4. Jumper wires to connect the HX711 module to the Arduino

## Circuit Connection

Connect the HX711 module to the Arduino board as follows:

- *HX711 DT/Output* to *Digital Pin 2 (Arduino)*
- *HX711 SCK/Serial Clock* to *Digital Pin 3 (Arduino)*
- *HX711 VCC* to *5V (Arduino)*
- *HX711 GND* to *GND (Arduino)*
  
## Wiring diagram
![image](https://github.com/Shivani9698/LoadCell_Weight_scale/assets/119753029/0fa5962f-8b07-4b83-a01f-23bebe63e64a)

## How to install library
1.We’ll use the HX711 library by bodge. It is compatible with the ESP32, ESP8266, and Arduino.

2.Open Arduino IDE and go to Sketch > Include Library > Manage Libraries.

3.Search for “HX711 Arduino Library” and install the library by Bogdan Necula.

![image](https://github.com/Shivani9698/LoadCell_Weight_scale/assets/119753029/18c2e803-8d54-4eb8-a792-b59ae9ecdcb8)



## How the Sketch Works

The Arduino sketch uses the HX711 library to interact with the HX711 load cell amplifier. Here's a brief overview of how the sketch works:

1. The HX711 library is included at the beginning of the sketch to enable communication with the HX711 module.
2. The HX711 circuit wiring is specified by defining the pins for data output (DT/Output) and serial clock (SCK/Serial Clock) connected to the Arduino.
3. The `setup()` function is used to initialize the serial communication at a baud rate of 57600 and set up the HX711 scale using the pins defined in the circuit connection section.
4. Various functions of the HX711 library are demonstrated in the `setup()` function:
   - The `read()` function is used to read a raw reading from the ADC of the HX711 module.
   - The `read_average()` function is used to print the average of 20 readings from the ADC of the HX711 module.
   - The `get_value()` function is used to print the average of 5 readings from the ADC minus the tare weight (not set yet).
   - The `get_units()` function is used to print the average of 5 readings from the ADC minus the tare weight, divided by the scale parameter (set with `set_scale()`).
5. The `set_scale()` function is used to calibrate the HX711 scale with a known weight. In this example, a calibration factor of -274.5 is set.
6. The `tare()` function is used to reset the scale to zero after calibration.
7. In the `loop()` function, the sketch continuously prints the average of 10 readings from the ADC of the HX711 module, representing the weight measurements from the load cell.

## How to Use

To use this Arduino sketch:

1. Connect the HX711 module and load cell to the Arduino board following the circuit connection mentioned above.
2. Open the Arduino IDE and upload the sketch to your Arduino board.
3. Open the Serial Monitor in the Arduino IDE (set the baud rate to 57600) to view the HX711 readings.

## Calibration and Scaling

To obtain accurate weight measurements, you may need to calibrate the scale with known weights and adjust the `set_scale()` parameter accordingly. Refer to the HX711 library documentation or the README for further calibration details.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- The sketch uses the HX711 library for interfacing with the HX711 load cell amplifier.
- HX711 Library: [https://github.com/bogde/HX711](https://github.com/bogde/HX711)


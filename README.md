<!-- Please do not change this html logo with link -->
<a href="https://www.microchip.com" rel="nofollow"><img src="images/microchip.png" alt="MCHP" width="300"/></a>

# RTC Crystal Error Compensation

This code example demonstrates how to do compensation for static drift. The drift is not measured, as it is static. Temperature is therefore not considered here. As this example uses a known value for the drift, the direction of the drift is also known.
The RTC is configured to generate an interrupt every second. In the ISR, a variable keeps track of the cumulative error. If the error is larger than one 32.768 kHz clock cycle, the RTC period is reduced to compensate for this.

This example is based on the Application Note [AN2711 - Real-Time Clock Calibration and Compensation on AVR® Microcontrollers](https://www.microchip.com/DS00002711), which should be referred to for a more detailed understanding of the concepts.

## Related Documentation

- [AN2711 - Real-Time Clock Calibration and Compensation on AVR® Microcontrollers](https://www.microchip.com/DS00002711)
- [ATtiny817 Device Page](https://www.microchip.com/wwwproducts/en/ATTINY817)

## Software Used

- [Atmel Studio](https://www.microchip.com/mplab/avr-support/atmel-studio-7) 7.0.2397 or later
- [ATtiny DFP](http://packs.download.atmel.com/) 1.6.316 or later
- AVR/GNU C Compiler (Built-in compiler) 5.4.0 or later


## Hardware Used

- [ATtiny817 Xplained Pro](https://www.microchip.com/DevelopmentTools/ProductDetails/attiny817-xpro)
- Micro-USB cable (Type-A/Micro-B)

## Setup

1. The crystal on the ATtiny817 Xplained Pro board is by default not connected to the TOSC pins, as they are used for UART communication. To connect the pins, remove resistors R307 and R308 and place them on the footprints of R312 and R313. Refer to [ATtiny817 Xplained Pro User's Guide](https://www.microchip.com/DS50002684) for more information on how to do this.

## Operation

1. Connect the board to the PC.

2. Download the zip file or clone the example to get the source code.

3. Open the .atsln file with Atmel Studio.

4. Build the solution and program the ATtiny817. Press *Start without debugging* or use CTRL+ALT+F5 hotkeys to run the application for programming the device.

## Conclusion

This example has now illustrated a way of compensating for static drift.

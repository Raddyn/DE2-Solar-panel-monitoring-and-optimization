# DE2-Solar-panel-monitoring-and-optimization

## Team members
- **Adam** (responsible for solar panel data collection)
- **Radek** (responsible for ADC, servo, photoresistor, timers)
- **Marek** (responsible for OLED, README, main loop, schematic)

## Description
Hardware and software solution for measuiring important data of a solar panel and capable of self rotation calibration based on photoresistor readings.


### Hardware list
- [Arduino Uno](https://store.arduino.cc/en-cz/products/arduino-uno-rev3?srsltid=AfmBOoovVZyf8qbg9ZrI9hX9NDjxxJZxmIjVDI9_GGtfzRbe-9TtOOlK)
- 
- [2W solar panel](https://www.seeedstudio.com/2W-Solar-Panel-80X180.html?srsltid=AfmBOop6e6pCLGFtqS4wp1RUDEjKHGq3ao6pdDNQLPoGoyCNA_wYi9g2)
- [Proudový senzor 5A ACS712](https://dratek.cz/arduino/1072-5a-proudovy-senzor-acs712.html?gad_source=1&gclid=CjwKCAiA3Na5BhAZEiwAzrfagO3sPKNKcjVXXOFWqBSw3VnbfjmYk3G59McyNn3DMNanhDyCYVnZrhoCHegQAvD_BwE)
- 
- [OLED display](https://dratek.cz/arduino/3181-iic-i2c-oled-1-3-displej-128x64-bily.html?gad_source=1&gclid=CjwKCAiA3Na5BhAZEiwAzrfagGTJY9aaMqUh7axe7fEJV2dWkBF2WsShhmveTVssdStMTSZZZww1mhoCKxMQAvD_BwE)
  
- relay
- resistors
- mikro servomotor

  

## Circuit schematic
![image](https://github.com/user-attachments/assets/8b63eb43-989a-42c1-b65c-ae2e348858ca)

### Libraries
- OLED.h
- adc.h
- servo.h
- gpio.h
- twi.h

## Instructions and photo

This project serves as an optimizer for the ideal orientation of a relatively close field of solar panels. This setup consists of a monocrystalline solar panel, a sensing and control circuit, along with a display. Depending on the illumination of individual photoresistors, the servo motor rotates accordingly, representing the orientation of the solar panel. This is a single-axis setup, meaning the circuit and corresponding software are designed for two photoresistors and one servo motor. The resulting necessary values for information purposes are displayed on a screen. Initially, an external memory module was also planned to store the acquired data. The circuit is designed to operate fully autonomously immediately after being put into operation. A servo motor controlled via PWM was used.


The photoresistors are connected in a voltage divider configuration according to the schematic. On both resistors, one contact is connected to a digital signal that acts as a switch. The resulting voltage is measured across a 1kΩ resistor. The resulting voltages are then sensed and compared. For the photoresistors under these conditions, it follows that their resistance can drop to approximately 300Ω when the sun is overcast. In complete darkness, their resistance reaches several kiloohms.


The current provided by the photovoltaic panel is measured using the ACS721-5A circuit. The circuit was originally designed for MPPT (Maximum Power Point Tracking) using the short-circuit current method, where the maximum is determined based on the short-circuit current provided by the solar panel. This current was initially supposed to be measured using a switching relay; however, due to time constraints, this was not implemented. Instead, this value was determined to be slightly over 3 mA under typical overcast winter conditions. This value is later used in subsequent calculations.


![image](https://github.com/user-attachments/assets/e28755d1-e475-4573-a805-734ec85c445e)


-![image](https://github.com/user-attachments/assets/41f0fb2b-c64f-4230-a750-7cfafa775cfd)

-![image](https://github.com/user-attachments/assets/911714fc-9677-45b7-876a-666120f85737)



## Results
We were able to succesfully compile and upload code to the Atmega 328p microcontroller, but correct functionality and desired precision would need further parameter tweaking. 

## References and tools
- [Simple Arduino Solar Radiation Meter](https://projecthub.arduino.cc/mircemk/simple-arduino-solar-radiation-meter-for-solar-panels-ae1531)
- [Chat GPT, Plus version](https://openai.com/)
- [Solarduino](https://solarduino.com/arduino-code-tips/)
- [avrfreaks](https://www.avrfreaks.net/s/topic/a5C3l000000UaPVEA0/t153755)
- [electronic wings](https://www.electronicwings.com/avr-atmega/atmega1632-pwm)
- [servo motor](http://www.ee.ic.ac.uk/pcheung/teaching/DE1_EE/stores/sg90_datasheet.pdf)
- Copilot for code commentary
- [Circuito - Arduino Uno schematic](https://www.circuito.io/blog/arduino-uno-pinout/)
  

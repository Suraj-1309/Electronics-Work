# Serail Plotter

one of the tools in Arduino IDE.  

Arduino can read the temprature, humidity or any kind of sensor data, and send it to Serial Plotter. Serial Plotter receives data from Arduino and visulaizes data as waveforms. 

Serial Plotter can not only visualize single but also multiple sensor data in the same graph.

Data is exchanged between Serial Plotter and Arduino via USB cable, which is also used to uplaod the code in Arduino . Therefore, to use Serial Plotter, we must connect Arduino and Pc via the cable.

  
  Serial plotter includes a selection box to select the serial baud rate and a graph:
  - **X - axis**: represent the time. It has 500 points. The time between each point is the time between two consecutive `Serial.println()` function calls. This time is usually equal to the time of `loop()` function.
  - **Y - axix**: represents the values received from Arduino. The Y-axis automatically adjusts itself as the value increases or decreases.

  

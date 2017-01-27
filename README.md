# GroveLoudnessSensor
Loudness Sensor Library for Arduino + Grove shield

[Link to the tested grove module](http://wiki.seeed.cc/Grove-Loudness_Sensor/)

##Example
```c++
#include <Grove.h>
#include <GroveLoudnessSensor.h>

GroveLoudnessSensor loudnessSensor(GROVE_A2);

void setup() {
  loudnessSensor.initialize();
  Serial.begin(9200);
}

void loop() {
  Serial.println(loudnessSensor.getNoiseAmount());
  delay(500);
}
```

##Documentation

###`GroveLoudnessSensor(GrovePin pins, unsigned int maxMesurement = 1023)`
Parameters:
- `pins`: Must be a analog socket (GROVE_A0 to GROVE_A3)
- `maxMesurement`: A number between 0 and 1024 corresponding the the maximum noise intensity at the output of the A/D sensor

###`void initialize()`
Initialize the sensor before using it.

###`float getNoiseAmount()`
Return the amount of noise from 0 (no noise) to 1 (maximum noise).

###`void setMaxMesurement(unsigned int maxMesurement)`
Set the maximum value the noise intensity.

Parameters:
- `maxMesurement`: A number between 0 and 1024 corresponding the the maximum noise intensity at the output of the A/D sensor

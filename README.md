# HC-SR04-Ultrasonic
This is an Arduino library for interfacing with the HC-SR04 Ultrasonic module

To use the library, declare Ultrasonic objects for each of your modules.
`Ultrasonic myUltra(int trigPin, int echoPin);`
The trigPin and echoPin are labeled on the HC-SR04 ultrasonic module. The echoPin must be on an interrupt pin of the Arduino.

To get data use this code:

```
myUltra.trigger();
int distance = myUltra.getLastDist();
```

If you are not sure if you have retrieved data from an Ultrasonic object recently and you only want one copy of the data, use this code:

```
if(myUltra.checkEcho())
	distance = myUltra.getLastDist();
```
  
Calling trigger() will update the values returned by getLastDist() and getLastTime() - make sure to call trigger() when you want to read the sensor.

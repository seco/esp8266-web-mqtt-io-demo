# ESP8266 Web Server + MQTT I/O Demo

## Objective

Create a IoT device that can have a pretty local web server to interact with the I/Os and also MQTT to interact with the internet (Currenlty using Adafruit IO)

## Phisical components

- 1 ESP8266 web enabled microcontroller (with USB serial and power)
- 1 DS18B20 Temperature sensor (with resistor)
- 1 RGB Led (with 3 resistors)
- 1 2-way relay board
- 1 Button (with resistor)

## Details

The code uses the flash file system to store the internal web page (using milligram and normalize as a pretty but light web framework). The internal web server is also Apple Web App compatible, this means that you can create a shortcut in an iOS device and it will behave as an app.

All the I/Os can be seen or controlled from the internal web page (that uses a lightweight local REST API that could also be called with simple json messages) or from MQTT pubs and subs to Adafruit IO, this allow to link it to other things using the Adafruit IFTTT channel.

The MQTT feeds that it uses are:

 - {user}/feeds/{chipId}-temp 
 - {user}/feeds/{chipId}-relay1 
 - {user}/feeds/{chipId}-relay2
 - {user}/feeds/{chipId}-led-rgb
 - {user}/feeds/{chipId}{user}/feeds/{chipId}-toggle-button
 - {user}/feeds/{chipId}-toggle-button-state

# Web page details

 - Responsive (Desktop/Table/Phone compatible)
 - Minified
 - Uses micro frameworks
 - Uses ajax
 - Auto refreshes itself
 - Allows to edit the chipId
 - Allows to send RGB colors
 - Allows to set ON/OFF each relay
 - Shows the current temp value
 - Shows the current button value (each time the button is pressed the value changes)

## TODOs

- Use secure MQTT
- Clean up the code

## See it in action

[![IMAGE ALT TEXT HERE](http://img.youtube.com/vi/DuW8WqxejXM/0.jpg)](http://www.youtube.com/watch?v=DuW8WqxejXM)

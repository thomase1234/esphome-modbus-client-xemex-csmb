** This is work in progress **

# esphome-modbus-client-xemex-csmb
ESPHome Modbus Client/Master component to pull info from the Xemex CSMB

## Goal
This project pulls information from an [Xemex CSMB](https://xemex.eu/products/meters-sensors/csmb/) and feeds it into [HomeAssistant](https://www.home-assistant.io/).

## ESPhome YAML config

Of course, this should be adapted to your board etc, but the modbus config can be re-used as is.
[YAML Config](/modbus-client-xemex.yaml)

## Used hardware

### The ESP32 Board I used

Link to [Azdelivery.de](https://www.az-delivery.de/en/collections/alle-produkte/products/esp32-developmentboard)

![ESP32 NODEMCU](https://raw.githubusercontent.com/thomase1234/esphome-modbus-client-xemex-csmb/main/pictures/esp32-nodemcu-module-wlan-wifi-development-board-mit-cp2102-nachfolgermodell-zum-esp8266-kompatibel-mit-arduino-872375_400x.webp)

### The RS485 module I used

Link to [amazon.com.be](https://www.amazon.com.be/-/nl/Fasizi-RS485-adapter-seri%C3%ABle-aansluiting/dp/B09Z2GTMJ8/)

![RS485-module](https://raw.githubusercontent.com/thomase1234/esphome-fake-xemex-csmb/thomas-dev/pictures/RS485_Adapter.jpg)

## Caveats

It looks like the reported current on the 3 "RMS Current CTx" is always positive. Even if electricity is being delivered to the grid the device reports a positive current. I don't there is a way to know if the CT is measuring electricity consumption or production.

## Sister projects

[Emulate a Xemex CSMB](https://github.com/thomase1234/esphome-modbus-client-xemex-csmb)


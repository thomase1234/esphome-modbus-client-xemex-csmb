** This is work in progress **

# esphome-modbus-client-xemex-csmb

ESPHome Modbus Client/Master component to pull info from the Xemex CSMB

## Goal

This project pulls data from an [Xemex CSMB](https://xemex.eu/products/meters-sensors/csmb/) and feeds it into [HomeAssistant](https://www.home-assistant.io/).

## ESPhome YAML config

[YAML Config](/modbus-client-xemex.yaml)  
Of course, this should be adapted to your board etc, but the modbus config can be re-used as is.

## Used hardware

### The Xemex CMDB

https://xemex.eu/products/meters-sensors/csmb/  
https://xemex.eu/wp-content/uploads/2021/07/User-manual-CSMB-1.0.pdf  
Page 9 of the user manual contains info on the supported modbus functions.

Note that this module is also used by the [Shell Recharge Advanced 3.0 Wallbox](https://shellrecharge.com/nl-nl/thuis-laden/advanced) for its Dynamic Power Management.

### The ESP32 Board I used

Link to product page on [Azdelivery.de](https://www.az-delivery.de/en/collections/alle-produkte/products/esp32-developmentboard)

![ESP32 NODEMCU](/pictures/esp32-nodemcu-module-wlan-wifi-development-board-mit-cp2102-nachfolgermodell-zum-esp8266-kompatibel-mit-arduino-872375_400x.webp)

### The RS485 module I used

Link to product page on [amazon.com.be](https://www.amazon.com.be/-/nl/Fasizi-RS485-adapter-seri%C3%ABle-aansluiting/dp/B09Z2GTMJ8/)

![RS485-module](/pictures/RS485_Adapter.jpg)

## Sample output

Note that CT2 and CT3 are not connected to my Xemex CMDB

[Raw Serial logs](/sample_output/output.log)

![Home assistant Sensors](/sample_output/homeassistant_device.png)

![home assistant sensor graph](/sample_output/sensor_graph.png)

![ESPHome Webserver Output](/sample_output/esphome_webserver.png)

## Caveats

It looks like the reported current on the 3 "RMS Current CTx" is always positive. Even if electricity is being delivered to the grid the device reports a positive current. I don't there is a way to know if the CT is measuring electricity consumption or production.

## Sister projects

[Emulate a Xemex CSMB](https://github.com/thomase1234/esphome-fake-xemex-csmb)

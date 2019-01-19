# Developers


## Code layout

The code is managed and developed using [Visual Studio Code](https://code.visualstudio.com/) [Multi-root Workspaces](https://code.visualstudio.com/docs/editor/multi-root-workspaces) and [platform.io](https://platformio.org/)
This combination allows to develop the server side (and sync updates using ssh extension called [sftp](https://marketplace.visualstudio.com/items?itemName=liximomo.sftp)) and the arduino station, including the bootloader code, compilation and flashing, all in one place.
It also offers tasks to compile and flash the bootloader and even a predefined theme.
[platform.io](https://platformio.org/) also allowed my to have a common networking code for all Arduino stations in one common directory which all Arduino projects (stations) can reference, keeping the protocol updates and changes easy and safe.

## Tasks & Bugs

This Project is managed with [trello](https://trello.com/b/8ODwVl67/diy-smart-home)

For issues and bugs please open on [Github](https://github.com/benchuk/SmartHomeDIY/issues)

## System layout

Controlling you home is done via a web application from your phone browser or any other browser.
The web application is hosted on a Raspberry Pi station, running Nodejs.
Nodejs 'talks' to a serial bluetooth attached to the Raspberry Pi 
![GPIOs](https://github.com/benchuk/SmartHomeDIY/blob/master/SmartHome/Other/Models_Images/PI_STATION/pi-to-bt-connections.JPG?raw=true)
the Serial Bluetooth sends the data to an arduino station gateway which dispatches the messages to
the relevant Arduino endPoint station using RF24 module.
each endpoint station has a unique address and a set of command it knows to handle.

## Flashing remote station from 'Visual Studio Code' script (task) TBD

* `Connect Flasher to computer
* `Ctrl+P and select Set remote Address this will set remote address to the Flasher.
* `Upload sketch (this will forward the sketch to the remote station with the specified address)


## IR Universal Station (<a href="http://www.ibroadlink.com/" target="_blank">Broadlink</a> or  <a href="https://www.logitech.com/en-us/product/harmony-hub" target="_blank">Harmony hub</a> like) ###
![IR](https://github.com/benchuk/SmartHomeDIY/blob/master/SmartHome/Other/Models_Images/IR_STATION/IR_STATION_MODEL1.PNG?raw=true)

## PI Server with node and serial commands sent using bt to bt to rf24 gateway/dispatch station ###
![PI_STATION](https://github.com/benchuk/SmartHomeDIY/blob/master/SmartHome/Other/Models_Images/PI_STATION/PI_STATION_MODEL1.PNG?raw=true)
![GPIO](https://github.com/benchuk/SmartHomeDIY/blob/master/SmartHome/Other/Models_Images/PI_STATION/pi-to-bt-connections.JPG?raw=true)


## Gateway: BT to rf24 dispatch system ###
![BT_To_RF24](https://github.com/benchuk/SmartHomeDIY/blob/master/SmartHome/Other/Models_Images/BT_TO_ANT_DISPATCH_STATION/BT_To_Ant_Dispatch_Station_model_bb.jpg?raw=true)


## Bootloader with OTA Capabilities

* `ctrl+p Compile Bootloader with OTA Capabilities
* You have to bootloader option: with auto reset option and without auto reset option - to learn more read [Here] about Arduino watchdog timer.
* `ctrl+p Burn the compiled bootloader using the AVR flasher to learn more read [Here].

* My [YouTube video](https://youtu.be/8xJqVeZkEw8) to get more info.
* Also read [here](https://www.2bitornot2bit.com/blog/arduino-bootloader-with-ota-over-the-air-support-over-nrf24l01) to get a better understanding 

## Bootloader modifications for OTA
<a href="http://www.youtube.com/watch?feature=player_embedded&v=8xJqVeZkEw8
" target="_blank"><img src="http://img.youtube.com/vi/8xJqVeZkEw8/0.jpg" 
alt="Arduino OTA" width="340" height="280" border="20" /></a>



## How to install

* [Download and install Visual Studio code](https://code.visualstudio.com/download)
* `git clone https://github.com/benchuk/SmartHomeDIY.git` - clone project.
* `mkdocs build` - Build the documentation site.
* `mkdocs help` - Print this help message.

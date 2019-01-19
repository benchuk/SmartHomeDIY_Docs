# Developers


### Code layout ###

The code is managed and developed using [Visual Studio Code](https://code.visualstudio.com/) [Multi-root Workspaces](https://code.visualstudio.com/docs/editor/multi-root-workspaces) and [platform.io](https://platformio.org/)
This combination allows to develop the server side (and sync updates using ssh extension called [sftp](https://marketplace.visualstudio.com/items?itemName=liximomo.sftp)) and the arduino station, including the bootloader code, compilation and flashing, all in one place.
It also offers tasks to compile and flash the bootloader and even a predefined theme.
[platform.io](https://platformio.org/) also allowed my to have a common networking code for all Arduino stations in one common directory which all Arduino projects (stations) can reference, keeping the protocol updates and changes easy and safe.

# Tasks & Bugs

This Project is managed with [trello](https://trello.com/b/8ODwVl67/diy-smart-home)

For issues and bugs please open on [Github](https://github.com/benchuk/SmartHomeDIY/issues)

# system layout

Controlling you home is done via a web application from your phone browser or any other browser.
The web application is hosted on a Raspberry Pi station, running nodejs.
nodejs 'talks' to a serial bluetooth attached to the Raspberry Pi GPIOs
the Serial Bluetooth sends the data to an arduino station gateway which dispatches the messages to
the relevant Arduino endPoint station using RF24 module.
each endpoint station has a unique address and a set of command it knows to handle.

### Flashing remote station from VSCODE script (task) TBD ###

* My [YouTube video](https://youtu.be/8xJqVeZkEw8) to get more info.
* Also read [here](https://www.2bitornot2bit.com/blog/arduino-bootloader-with-ota-over-the-air-support-over-nrf24l01) to get a better understanding 



### How do I get set up? ###

* -------- TBD ---------
* -------- TBD ---------
* -------- TBD ---------
* -------- TBD ---------
* -------- TBD ---------
* -------- TBD ---------



### IR UNIVERSAL STATION (broadlink or harmony hub like) ###
![IR](https://github.com/benchuk/SmartHomeDIY/blob/master/SmartHome/Other/Models_Images/IR_STATION/IR_STATION_MODEL1.PNG?raw=true)

### PI SERVER WITH NODE AND SERIAL COMMANDS SENT USING BT TO BT TO RF24 DISPATCH STATION ###
![PI_STATION](https://github.com/benchuk/SmartHomeDIY/blob/master/SmartHome/Other/Models_Images/PI_STATION/PI_STATION_MODEL1.PNG?raw=true)
[GPIO](https://github.com/benchuk/SmartHomeDIY/blob/master/SmartHome/Other/Models_Images/PI_STATION/pi-to-bt-connections.JPG?raw=true)


### Gateway: BT TO RF24 DISPATCH SYSTEM ###
![BT_To_RF24](https://github.com/benchuk/SmartHomeDIY/blob/master/SmartHome/Other/Models_Images/BT_TO_ANT_DISPATCH_STATION/BT_To_Ant_Dispatch_Station_model_bb.jpg?raw=true)

### Bootloader modifications for OTA

<a href="http://www.youtube.com/watch?feature=player_embedded&v=8xJqVeZkEw8
" target="_blank"><img src="http://img.youtube.com/vi/8xJqVeZkEw8/0.jpg" 
alt="Arduino OTA" width="340" height="280" border="20" /></a>


Planned features list:

- [x]  IR - 'Broadlink' or 'Harmony hub' like - records IR commands and send them on request.
- [x]  Control and configure Smart House using nodejs website from mobile.
- [x]  Node Running on Raspberry Pi using serial to send commands to other Arduino using the Bluetooth HC05 (serial to Bluetooth chip).
- [ ]  Auto light using light sensors.
- [ ]  Plants Water system (time and light configuration)
- [x]  Shutters control.
- [x]  Shades control.
- [x]  House Light control
- [ ]  Clap to turn off/on lights.
- [ ]  Security camera and streaming.
- [ ]  Music remote control.
- [ ]  Hot water auto and timer control. (turn boiler for x hours - or everyday from hour to hour)
- [ ]  LCD Screen on main arduino to monitor and status.
- [x]  On wall Touch switch in parallel to digital control.
- [ ]  IR Control for Air Condition - temp sensors. weather forecast and outside temperature and humidity - start Air Condition for x hours and auto close - with temp variation plans.
- [x]  Remote update the other Arduino station from RF24.
- [ ]  Send notifications when dish washer is done (no power consumption)



## How to install

* [Download and install Visual Studio code](https://code.visualstudio.com/download)
* `git clone https://github.com/benchuk/SmartHomeDIY.git` - clone project.
* `mkdocs build` - Build the documentation site.
* `mkdocs help` - Print this help message.

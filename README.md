# KiWi.Docs
Documentation and notes for different modules

## KiWi.Deadbolt
#### Option 1
- ATMEGA328 Microcontroller programmed using Arduino
- LM400 Bluetooth dongle
- Power suppy TBD

##### Networks
- [x] Mobile <--> Deadbolt (Bluetooth)
- [x] Mobile <--> Server (Wifi or Bluetooth)
- [x] Server <--> Deadbolt (Bluetooth)

####To Sum Up
System is larger but easy to develop. Bluetooth interaction can get difficult at times. Auto-unlock feature will be genuinely based on Bluetooth distance (however this is not as reliable as one might hope). Lots of code help (NerdKits) and shouldn't be too hard to develop overall.

----

#### Option 2 (Optimized)
- Attiny2313 Microcontroller programmed using Arduino Uno
- XBee communication protocol
- Power suppy TBD

##### Networks
- [ ] Mobile <--> Deadbolt (No direct communcation!)
- [x] Mobile <--> Server (Wifi or Bluetooth)
- [x] Server <--> Deadbolt (XBee)

####To Sum Up
System is small, power efficient, and fast. Auto unlock feature WILL rely on location along with Wifi or Bluetooth. Personally, I don't know how to couple this specific microcontroller with XBee but I assume it is possible. We completely ditch the Bluetooth protocol. And ZigBee XBee is a more power efficient system according to papers like [Power Consumption of Wireless Protocols](http://research.microsoft.com/pubs/192688/IWS%202013%20wireless%20power%20consumption.pdf). This would be considered as an "actual" project because there is some research that needs to be done but nothing that cannot be completed within a couple of months.

----

#### Option 3 (Focus on software)
- Arduino Board
- RedBear BLE Shield
- Power Supply TBD
- DC Brushless Arduino Compatible Motor

#### Summary
This system focuses on software more than hardware. Auto unlock feature will work based on GeoFencing and BLE on an Android/iOS device. System will be slightly large but not too shabby. This will cut the time it takes to print out a PCB board, solder, etc. We can make a more beautiful App and WebServer while still maintaining the hardware functionality we require. If we get time we can build a PCB board for proof that it can be easily optimized into a smaller system. Connecting with BLE is realitively simple and there are many tutorials online.

####Miscellaneous
- Android platform should be first choice. It has many support utilites like BlueTerm which help development a lot more efficient. If we have time, we can consider IOS.
- With both options, the PCB board must be designed in advance. We can potentially ask for some contractor to design it for us granted our parts work as intended on a breadboard first.
- Power supply is a major concern. For a decent usage, 3 AA batteries can power the deadbolt (but we can reduce that down to one (1) if possible at least for the demo.
- NerdKit might be something we are interested in buying
- [Pinnochio](https://pinocc.io) is a slightly easier (and pricey system) which can be our failsafe. Watch a video [here](http://www.youtube.com/watch?v=TYj5OHki9ss). I feel that any idiot can make our system with this, so let's not do this.
- Development needs to be parallel. Each step below should be done together
  - Motor should be coupled with a simple board for now ensuring the power consumption, torque, etc. (Jesun + Caroline) (Finished by the end of Feb / start of March)
  - Microcontroller and communication protocol must be developed together with the server and Android app (Kapil + Mathew) (Finished by the end of Feb / start of March)
    - Will also require a PCB design (Start process at the beginning of March)
  - Power supply optimization (Xun + Nick) (By mid of March)
- Development for XBee modules can be made easier with the [XBee library](https://code.google.com/p/xbee-arduino/)
- [Integrating BLE with iOS Swift](http://www.raywenderlich.com/85900/arduino-tutorial-integrating-bluetooth-le-ios-swift)
- Control RGB Lights from Android & BLE [link](http://www.instructables.com/id/Control-RGB-lights-from-Android-with-Arduino-Bluet/)
- We can also consider the [Rasberry PI XBee module](http://www.cooking-hacks.com/documentation/tutorials/raspberry-pi-xbee) for developing the server

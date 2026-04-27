# ParaNode

This is a simplified and slimmed version of the CaveNode, sacrificing waterproofing and durability (at least in version 1) 

It has an integrated BT antenna, which is good to 15m, and an integrated GPS antenna.

## Features 
- 103040 Battery (4 days runtime with GPS)
- GPS 
- LoRa Antenna
- BT (10m range)
- easy on/off switch

## PCB Features 
- RGB status LED 
- Integrated BT Antenna 
- Integrated GPS 
- u.fl for Lora
- USB-C programming and charging 
- Integrated Battery protection
- provision for i2c, uart, and magnetic charge/program


## User Manual 

### Interfaces

LEDs
These are a little hard to see through the case, paricularly the green.

- Charging 
- Heartbeat 


Buttons 
- Reset 
- User 

### Operation

#### Turning On

#### Turning Off

#### Charging 
1. Ensure the device is on
2. Charge using the USB-C port
1. Charging is complete when the red charging LED extinguishes.

#### Use as a user device 
1) Aquire the *Meshtastic* App from your app store
2) Turn the device on by removing the battery clip
3) Take note of the last 4 digits of the device ID
4) Open the app
5) follow the tutorial to pair the device (last 4 digits will help find it) using bluetooth (default code: 123456)
6) You are now connected and can send / recieve messages

#### Use as a repeater
The ParaNode will automatically rebroadcast any meshtastic packets that match its preset. 

1) Turn the device on by removing the clip

2) Place the device in a suitable location

### Flashing firmware 
1) Aquire firmware from [the Flamingo releases](https://github.com/DaneEvans/Flamingo-Firmware/releases)
    - This board variant is currently known as the nswcrs, and has flamingo (cave) and regualar firware available. 
    - These releases may lag the official meshtastic releases, if this occurs please raise an issue in the repo.
2) Go to the [meshtastic flasher](https://flasher.meshtastic.org/) 
4) ensure the Node is plugged in
5) Select your own firmware file (the one from 1 above) *(choose RAK4631 if you want stock firware and are prepared to alter pins for all peripherals.)*
6) Press flash
7) Press the 'Enter DFU Mode' button on the website, or press the reset button twice to enter it manually
8) Flash the new firmware. 


## FAQ 
### Where can I get the latest firmware? 
https://github.com/DaneEvans/Flamingo-Firmware/releases

### How can I tell if I have the Flamingo or Vanilla firmware? 
On Android, Flamingo will report as a 'Custom' variant, and the Vanilla will report as 'Vanilla'.

### Why won't the battery charge

### Why won't the Node turn on / charge despite the clip being removed.

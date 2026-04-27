# CaveNode Basic

The simplest cave node, it's fitted with an 18650 for up to 7 days of battery. (likely with no LEDs)

There are 2 LEDs to help with network management and laying the radios.
A magnetic reed switch to turn them off

IP67 (non-rated, but tested)

The typical variant is shipped with a very poor bluetooth antenna, and is typically only used for short range (~1m) use to change settings. 

## Variants
### Internal Antenna
This is the most suitable for hostile environments. It likely has more blind spots, and less range, but by removing the additional breach in the case, we can reduce the possibilities for water ingress.

Dual TPU seals, fully contained.

### External Antenna
This is better for drier placements, and places where you need more range, or a more predictable radiation pattern. An antenna must be connected for operation.

### Bluetooth Antenna
This is not the default (V1), but an internal antenna may be added to extend BT range to ~10m

## Optional features
- GPS
- Magnetic charging / usb port


## User Manual 

### Interfaces

LEDs
These are a little hard to see through the case, paricularly the green.

- Charging 
- Heartbeat 
- RT 
- Conn


Buttons 
- Reset 
- User 
- Duress (not yet available)

### Operation

#### Turning On
Remove the magnet clip from the device and store it separately.
When the device turns on the RT and Conn LEDs will light up red, then green for 1 second (Flamingo FW) and the heartbeat LED will flash once per second while the device is on. 

#### Turning Off
Place the magnet clip on the device, aligning the keying marks. 
The heartbeat LED will cease flashing. 

#### Charging 
1) Remove the top cap in a clean, dry environment.
2) Ensure that the magnet clip has been removed.
3) Plug the device in with a USB-C cable.
4) The red charging light will be present while the device is charging, and extinguish when it is full. 
5) reseal device carefully, if the device is not to be in use, replace the magnet clip. 

#### Use as a user device 
1) Aquire the *Meshtastic* App from your app store
2) Turn the device on by removing the battery clip
3) Take note of the last 4 digits of the device ID
4) Open the app
5) follow the tutorial to pair the device (last 4 digits will help find it) using bluetooth (default code: 123456)
6) You are now connected and can send / recieve messages

#### Use as a repeater
The CaveNode will automatically rebroadcast any meshtastic packets that match its preset. 
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
Make sure that the magnet clip is off - it completely disconnects the battery to prevent discharging.

### Why won't the Node turn on / charge despite the clip being removed.
The battery management circuit will disconnect the battery to prevent damage to the battery. In the event that this occurs, it is possible that it will not reconnect when the Node is placed on charge, and the red light will not come on. 

If this occurs, place (2 seconds) and remove the magnet clip to reset the power to the management chip. 
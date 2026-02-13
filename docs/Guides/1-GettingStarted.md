# Getting Started with SpeleoMesh
Speleomesh is based on the open Source Meshtastic project, and is built upon the *Flamingo* firmware, initially developed for cave rescue use by Huntsville cave rescue in the USA.

The system uses a LoRa (Long range, low power) radio technology backbone, running on the 915MHz band.
Interfaces are provided via a phone app,  with some devices providing on board screens and/or keypads.

Practically, this means that an operator on the system needs a phone, and a small device slightly larger than an 18650 battery to connect to a network.

The network depends on the geography, above ground with a 500m AGL mountain, I have achieved 115km between two stock radios, with line of sight.
Underground we are a lot more limited, as the limestone blocks a lot of the signal.



## Getting on the system

### Get a device
Various options here, check [./2-Hardware.md]

### Download the phone app
Gplay  - Meshtastic

App Store - Meshtastic

### Connect to the device
Go to connections - bluetooth - Pin is 123456
*Note, only one device can conenct at a time, and it autoconnects. So if you are sharing a device, and having issues, make sure that only one phone/pc is connecting at a time.*

### Communicate
That's it, you are on the network.
If you are having any isses, ensure that you have the correct channels set up with the rest of your network.


## Updating firmware
You can use the Meshtastic Flasher - but we aren't using their firmware, as it doesn't support sufficient hops.
In step 2 ? you can change the targeted firmware.


Firmware is hosted at : github/DaneEvans/Flamingo-Firmware

Ensure you use the correct device.

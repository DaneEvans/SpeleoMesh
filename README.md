# SpeleoMesh
NSW Cave Rescue, NSW Australia.

## Purpose
Replace the aging Michiephone systems for rescue communications.

## Technology

Lora (915 MHz) radios, currently using Meshtastic as a protocol.

## Requirements
- Durability
- Long life
- Reliability 


## Trials 
[Tuglow October 2025](docs/trials/1025_Tuglow.md)

[Bungonia September 2025](docs/trials/0925_Bungonia.md)

## Technical details

### Hardware
I am currently trialling several different devices.
Mostly nRF52 variants, for better battery life.

- Seeed nRF kits
- Seeed T1000E
- Heltec V3
- Heltec 114

A far as off the shelf devices, the Heltec 114 is the best I've found, except it is not a sealed unit, but it's robust, and has decent battery life.
The T1000E would be great, but the lack of battery life is an issue.

For relay nodes, the nRF kits are substantially cheaper, or more likely we spin our own.
The Wio WM1110 module is a candidate.

Requirements

| Feature   |  Trunk    | Personal  |
| ---       | ---       | ---       |
| IP68      |  Y        | Y         |
| Battery life (days) | 3 (5 des) | 1 (3 des) |
| Off switch | Y        |  Y        |
| CO2 sensor | desired  |           |
| Temp sensor | desired | desired   |
| Man down button | desired | desired |
| Range      |   200m LoS |   200m LoS |
| Cost      |  50       |   50      |


### Firmware
We are running the Flamingo variant firmware. [Details here](docs/Firmware.md).
It is currently set up with CI actions to keep it up to date with meshtastic/firmware:master, and apply the Flamingo patch.


### Software
- Stock Meshtastic Android app
    - Set up with canned messages for the ADRT commands
- I think Flamingo has a logging script somewhere
- Python surface setup (coming soon)
- Programming scripts (coming soon)- presets, admin keys, channels. Node names etc.

## Similar Projects

[Flamingo](https://github.com/rbreesems/flamingo?tab=readme-ov-file) - Hunstville, Alabama
- Includes increased hop limits, and RS484 PHY links. 


[Vangelis](https://github.com/semper-ad-fundum/vangelis) - UK
- currently less active, but some reasonably extensive testing


## Pages config
Uses Jekyll. Hosted at https://daneevans.github.io/SpeleoMesh/docs/Firmware.html



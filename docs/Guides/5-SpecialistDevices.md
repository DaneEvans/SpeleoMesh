
# Specialist devices

## RS485
These enable the data to travel on a pair of wires between two devices. Use them in locations where a large number of radios / survey legs would be necessary to span the area; Serpentine canyons, loops in solid rock etc. 
For the most part we have had reasonable ability to get radio waves through rockfall, so attempt to use radios first. 

### Usage
Lay as usual for radio reception, and make sure that the wires are plugged in well. 

### Tricks
Both nodes on the end of the wire **must** be set to the same baud rate. Lower numbers are slower, but will travel further down the wires. 
9600 baud successfully travels through 80m of thin gauge wire. 

## Logger 
This logs all messages it sees to an SD card. It will allow analysis to determine proportions of messages that made it to each end etc. 

### Usage 
Place as a normal radio, where you want to log data. These are currenly not waterproof, and must be protected accordingly. 

## Surface Unit
This is a small single board computer that can be run on a 5v USB supply. 
It allows monitoring and network health indicators. 

### Usage 
Place as a normal radio, and allow it to autoboot. It comes up on a network that is programmed in, and will serve a website to raspberrypi.local:8080.
If you go to that page, you can adjust the autoreact settings (Secondary channels only) and set up or turn off Auto messages (used to set LED states)

Generally this should be placed at or near the entrance controller, as things like the network map (coming soon) will be potentially usefful to those operators. 


### Programming 
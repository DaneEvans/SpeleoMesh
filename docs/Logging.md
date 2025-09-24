# Incident logging

## Surface controller 
The PC/tablet at the top which is the portal inside to outside will be the primary logging and log viewing interface.

In areas where there is reception, it should also be possible to send packages to MQTT, logging on a server somewhere. 
In time I may be running and hosting one, and would just turn on a wifi connection for the node to set that up.

Would also allow for remote comms, but uses and procedures around that would be needed. 

## Logging at nodes 
The nodes have a serial interface at either 38400 (T114) or 115200 (Heltecs). This can be viewed with a serial terminal. 

Assuming there's no handhake, an OpenLog PCB tied into the serial pins could be used to log to card directly, maybe by doing one as a USB pcb. 

Wisblocks may have a logging port too... 

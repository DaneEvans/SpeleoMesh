# Firmware

## Repo setup

I have mirrored the current Flamingo 2.6 branch at 22 Sept '25 to my fork, and squashed it to a single commit. 

There is a sync_upstream action that runs on main on a schedule, and will keep the master and develop branches of my fork aligned to the upstream meshtastic ones.

It will also apply the Flamingo patch on top of it. Conflict handling has not yet been tested, but I believe it should fail. 

## Flamingo

At the moment I'm using the [Flamingo firmware](https://github.com/rbreesems/flamingo?tab=readme-ov-file) until our needs diverge.

They've added a few things to the branch, some of which we don't need at this point, but it's pointless to have more things to maintain, when we can just spread the load to do that. 

### Features
Flamingo uses Wisblock devices, and has added RS485 support which we don't plan to use, but may in future.

- Max hops increased to 31 (theoretical 255)
- Changes to range test
  - optional hopping packets (sent from surface, but may cause congestion)
  - ADRT commands to individual nodes via DM to turn on / off 
  - add RSSI to the packets.
- Changes to serial logging that improves readability
- Buzzer haptics for signal strength
- Changes to splash screen (supposedly - may only be the wisblocks)

## TODO list

- Neighbour info on request
- RGB light in response to rangetest packets.
    - I belive that the flamingo guys have plans for this too, but I can't find it now.

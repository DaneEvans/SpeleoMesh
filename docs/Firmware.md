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

- Neighbour info on request  -  I started a branch at feat/neighbour_rq
- RGB light in response to rangetest packets.
  - I belive that the flamingo guys have plans for this too, but I can't find it now.

## Testing

Currently built on firmware/**master** on 22/09/25 - ahead of tag v2.7.9.70724be

- Range test and range test commands are working.
- range tests have rssi - and it appears on the display on display nodes.
- need to check hops, but it should work fine
- We're not going to use rs485, at least at this stage.
- BT seems a bit unstable on this particular version on the 114

Moved back to the **2.7.9 tag**.

- definitely seems better. May stay there barring major stability improvements.

## Seeed Xiao BLE SENSE (not kit)
- Seeed Xiao ble sense boards are incompatible with meshtastic beyond 2.6.10 - at least as the seeed xiao kit.

Instead, we are building on 2.6.10 with FLAMINGO merged in at 07bb93907633cd3cdd8c23678e7492ca1abc8950 - beyond that needs the define of a pin for the buzzer, because it's not guarded, which needs to be rectified.


## Pinned versions for October '25 exercise

- Seeed Xiao Sense + SX1262  - 2.6.10 - tagged CRS_1025_2.6.10_nRF_sense - branch CRS_OCT_25_2.6.10
- Seeed Xiao (non-sense) + SX1262 - 2.7.9 ...
- All other architectures are based off 2.7.10, merging 'hopmod_2.6.11' at c1c68a333f728af433ed88b6e79723ba2f387261. Tag: CRS_1025_2.7.10
- All firmwares are in ../firmware.

Programming settings is done through a modified version of the programmer in the Flamingo repository. The config file will not be included, as it contains secrets.

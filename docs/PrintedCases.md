# Printed Cases

Notes about the cases found on Bambu studio / other locations 

## Heltec V3 

### 2x 18650 case
Not awful. It's a dense case, but not too much excess space, and fits 2x18650s.

Minor things
- prints with overhangs. buit not awful. 
- SMA hex only fits through in one spot. (uneeded)
- nothing to hold batter wiring in place

Changes:

- Reset button could be recessed more.
- Could do with  more space around batteries to allow easier wiring, and to fit a PCB antenna inside. 
- Hard to get 2 batteries in if they are already tethered together. 
- Needs a tether location, or 2.
- Wave design is unnecessarily complicated.

- ufl - SMA needs to be 2cm, 5 has some hard bends.


## nRF52

### Cylinder - single 18650 
Close to the plan we'd considered.

It's a good design, but it needs a bit of DFM 

Pros: 
- 18650, nRF, off the shelf
- USB port is sealed away 
- an Oring ould seal it
- good wiring channel


Cons: 
- So much printing... the full length internal sleeve is excessive, with a full length outer, and long endcap 
- Indicator LED is covered
- The SMA port goes through both shells - you can't pull it apart without taking it off. 
- Lid is very bulky, and should print the other way up. 
- Button works well, but is hidden behind the endcap. 
- outside sleeve is so long that you can't grab the inner
- tolerances are too tight around the pcbs.
    - need to install the radio, then the antenna, then the battery cables, then solder to the uC, then install uC pcb. 
    - some more intelligent routing and space would make it easier
- no keying on SMA
- some prints the wrong direction.
- The keying is excessive, and adds to the overall diameter
- Textured finish is slow to print
- PCB stack is the larger orientation
- some alterations would make battery terminals easier to install. 
- If SMA sat above the battery, you could shave 6 or so mm off the internal
- internal sleeve prints in wrong orientation 




### Flat - 103040

This can take a larger battery too

Not suited to the nRF radio - button is in the wrong place.
Needs <5cm antenna tail no matter whether you go SMA or PCB

Pros:
- Solid and dense
- Good tether
- Uses the SX1262 and Xiao in the smallest way - needs things to arrive unsoldered to make things easier.
- Flat will fit better in pockets.
- Space for a PCB antenna internally

Cons: 
- Very low tolerances around the PCBs.
    - Stack height needs to be a minimum, and smoothed on top
    - The button doesn't fit - as well as being in the wrong place
- lots of unused space (and excess plastic) 
- Prints in the wrong orientation, and needs supports 
- SMA cable traverses halves,
- nothing to lock halves together
# Tuglow Major Exercise - October 2025

## Objectives
- A full scale test, including layout, to determine whether we can successfully get messages through a useful number of hops.
- Use the text platform in an exercise and prove it's use and practicality
- test the Flamingo firmware

## Tuglow T1


18/10/2025 - 1030 - 2030 

![T1](./images/Tuglow_T1.jpg)

18 radios available, on ShortFast, using Flamingo firmware, with max hops 32. 

1 - DES3 - The first radio - DES3 was placed in a tree over the covered entrance. This was a few meters above to get coverage around the immediate area for the surface team. 

2 - CRS4 - This allowed a relatively straight passage to the top of the major pitch, where CRS4 was placed.
  - at this point, my T1000E was reading DES3 at RSSI -100, SNR 10

At this point word came back from the Hasty team, and a message was successfully transmitted to the surface by Brian, ahead of the Michie messages as it was stalled on the pitches due to traffic.

As the mesh was the only functional system to the surface at that point, I turned off the range test function on CRS4 to allow traffic through it, and once the ropes cleared I headed down. Unfortunately the node that ChickenLegs was paired to was still in my bag at that point, so in descending the ropes, I cut our easy communication as well. 

3 - CRS2 - From there, the pitch drops down a steep narrow rift, into a slightly larger chamber, before constricting again. I placed CRS2 in this chamber, asking Chickenlegs to position it when he got there, if I couldn't get a direct path to CRS 4 

4 - DES1 - the rift continues along much the same trajectory to the river below. I placed another of the solar nRF kit nodes approximately 8 meters above the floor, on a stalagmite where it had a decent view both up and down the streamway.

From there, I tried to assess the communication back up the rift as Chickenlegs repositioned CRS2. Things appeared to be only marginal, but without a means of communicating, he came down to the river. 

Once he joined, we established that we had a broken, or weak link up towards the surface - occasionally it would be filled, possibly by our nodes, Alex's, or another one. He positioned more along the streamway, and I attempted to get up the ropes to have another go. Unfortunately there was a lot of traffic coming down, and I was unable to do so for quite some time, eventually going up the alternate (down only) route that Team 2 had rigged, and getting a heltec node near the bottom of there that seemed to fill the gap up to CRS4.

I returned down, and liased with the various teams at the bottom.
We still seemed unable to talk to the surface, so I went up again, going all the way up the alternative route, to check the link above CRS4, and it seemed that DES3 was not reaching as far into the cave. I placed another node into that gap, and handed my tablet and the Heltec 114 to Ruth on the surface as Rod's surface node was nearly flat. 
I suspect that as DES3 heated up in the sun, it's noise floor increased, and reduced the range to CRS4. 

The other heltec - filling the gap partway up the alternate was also running out of power, and I had to return to the bottom, and then back to add a power pack to it. 

I also repositioned, and added a pair of radios in the middle where CRS2 was, adding a radio with a     5m cable to a 1/8 antenna, mostly because several of the little helical antennas had broken, and I was running out of radios. I meant to use either the leaky feeder, or 5m antenna, but apparently grabbed the wrong one.

### Observations 
- I need to know the expected battery life of all radios
- We need spare antennas 
- Shutting down the range test packets was a bad idea, network usability is not improved if the placement isn't great. 
- All nodes need tethers - Chickenlegs had them, so my repositioning was done without. 
- Solar nodes may be adversly effected by heat.
- The 2dB threshold that I had established at Bungonia, and that the HCRG quoted were established on Longfast, and medium fast. We were on shortfast, and I should have been more conservative with placement, especially on the first hop.
- Positioning without a drill is incredibly hard on vertical caves. Recommend not doing that again. a 2mm drill bit + toothpicks, or a 6mm + dowels is definitely a requirement.
- There are situations where the option for leaky feeders, or dual antennas may solve issues. 
- I believe that our issues with CRS4 to CRS2 and DES1 may have been exacerbated by humans at the pitch head - Radio would have been going through a 0.3 x 1 m gap at the pitch head, that often had people in it, especially when doing the hauls on that pitch. Short range traffic had no issues in that area - Dave and I spanned it on the first haul with no issues, but were both above it for the later haul.





### Node allocation 
- Dane - MeshComms, T1000E
- Chicken Legs - MeshComms, nrfkit
- Brian - Team 1, nrfkit 
- Alex - Team 2, T1000E
- Dave T - Team 3, Heltec 3
- Rod - Surface command - Heltec3
- Ruth - Surface command - Heltec 114 (about halfway through)

### Hardware 
17 radios:
- 2x Seeed T1000e 
- 6x Heltec v3
- 1x Heltex 114 
- 8x Seeed Xiao nRF kit based radios with either 18650 or 103040 batteries.

### Firmware
[Flamingo firmware](https://github.com/DaneEvans/Flamingo-Firmware), using the crs1025 tags. 
Max hops was set to 32, 

### Software
Meshtastic Android, 2.7.4, +- 1 version
Meshtastic Apple, at mid October 2025


### Battery Life
As we already know, the ESP32 based Heltec 3 boards use a lot of power.
The new Heltec 4 is not any better from the numbers that I've seen.

Mine, with 2 18650 batteries, last approximately 36 hours.
The additional ones provided by other members had smaller batteries, and in the case of one pair, they did not make it through the entire exercise without needing a usb battery pack.

*Recommendation* Do not purchase any more ESP boards, or recommend their use. There are some benefits to the screen and the price, but until the power consumption of them is fixed, they aren't suitable for our purposes.

### Conclusions
The system performed reasonably - the failure of the other systems lead to it being promoted above it's planned use very quickly, and caused it's setup to be rushed, and done with less precision. Most complaints were about lack of access to the system, not it's performance.

The signal quality numbers I was targetting were not customised to shortfast. It's possible that moving back to MediumFast would be a good idea. 

It was useful in both getting messages to the surface, and was used extensively in adhoc arrangements.

We had very few issues underground, and no known missing messages or holes in the network, except the last few hops to the surface. 

Being behind the michie may not have been a good idea, they were already delayed, but are slower to deploy than the mesh, especially to allow the Hasty team to make reports. This was exacerbated by the constricted, and vertical nature of the cave.

### Recomendations 
- Need consistent hardware 
- rangetests need better feedback 
- need to automate checks on network health 
    - auto thumbs up / robot from surface node
    - set a green light on the node itself - set from surface. 
- more people need personal nodes
- nodes need power switches - look at reed switches. 
- Bright colours are essential
- Another channel needs to be enabled for adhoc comms to reduce chatter. 
- Need to prioritise laying the system before prioritising messages. Getting the first message through was important, but shouldn't have been allowed to compromise the network.
- Turn on client_mute on all personal nodes, to make it easier to see holes in trunk systems. 
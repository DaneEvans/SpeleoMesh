# Bungonia - September 2025

## Objectives



## Blowfly
14/9/2025 0940 - 1020 

6 radios, preset LongFast
Top Radio was a NRF kit `DEtS`, with antenna at the rap bolts at the higher entrance. The end point radio was a t1000e, with the others used as intermediaries.

A radio 'DEtB' was placed between the two pitches, approximately a meter above the single bolt. 

one was placed at the bottom of the pitch, and another where connection to that one became patchy. 

After coming back up through the spokeshave, we were still getting connection to `DEtB`, and the 5th radio was placed at the top of the Dragons teeth. 
From there, I was able to extend the final radio to the bottom of the chamber starting the Dragons teeth.

``` text
TraceRoute from the bottom of the dragons teeth:
Route traced toward destination:

■ DEV card t1000e (DEVa)
⇊ ? dB
■ Meshtastic ffff (ffff)
⇊ 4.25 dB
■ Dev nrfB batt b46d (DEtB)
⇊ 3.0 dB
■ Dev nrfC Solar 3234 (DEtS)

Route traced back to us:

■ Dev nrfC Solar 3234 (DEtS)
⇊ 2.25 dB
■ Dev nrfB batt b46d (DEtB)
⇊ 4.75 dB
■ DEV H3 10f8 (10f8)
⇊ -3.0 dB
■ DEV card t1000e (DEVa)

Duration: 23.2 s
```

### Conclusions

With the two redundant radios moved to the end of the chain, we likely could have closed the loop on blowfly with 6 radios, but we may have had blindspots in the lower secion between the pitches and the spokeshave. 
In their placements as we set them, it would have taken 8-9 radios to close the loop.

It took 2 people 40 minutes to lay the radios in Blowfly, despite using stock software that limits the frequency of traceroute messages, and no user experience optimisations. Including turning off radios that are not yet placed.


## Grill, B14
14/9/2025  1140 - 1237

5 working radios (one of the NRF kits was suffering. )
Changed preset to Medium Fast for faster communication, but less range (still likely to be 3km LoS).

Grill was a far more linear cave, selected to look more at range, and reduce the chances of cutting off part of the loop. 

The `DEtS` surface node was placed in the daylight hole in the doline below the entrace.
5 radios got us almost to Crystal Palace. With a bit more tuning of placements, it liklely could have. Laying the 5 radios, and retrieving them took approximately 1 hour, including some issues with the uncooperative node.

We were able to push the radios to lower signal strengths with more space, and straighter passage, but kept decent reliability down to ~-15dB.

The failing node caused grief, as the current Meshtastic protocol is suceptible to a 'bad' radio retransmitting signals in ways that reduce the likelihood of getting a signal out. We likely would have found this sooner had there been additional traffic from the surface, and certainly having the ability to turn off nodes would have made it more obvious, and solving it easier.

>**Note:**
>Meshtastic encourages messages further into the mesh rather than bouncing around the same area by two means:
> - 1 A Node will not retransmit if it has already heard a retransmission from another node
> - 2 The time to retransmission is inversly related to the strength of the recieved signal.
> 
> This means that a poor antenna, that is within range of a good repeater may 'swallow' a message, and prevent it's transmission onto the next node. 

```
Traceroute to surface from 3 hops in (max hops in FW)
Route traced toward destination:

■ DEV card t1000e (DEVa)
⇊ ? dB
■ Meshtastic ffff (ffff)
⇊ -15.5 dB
■ Dev nrfB batt b46d (DEtB)
⇊ 3.25 dB
■ Dev nrfC Solar 3234 (DEtS)

Route traced back to us:

■ Dev nrfC Solar 3234 (DEtS)
⇊ 1.75 dB
■ Dev nrfB batt b46d (DEtB)
⇊ -13.25 dB
■ DEV Van H3 10f8 (10f8)
⇊ 12.25 dB
■ DEV card t1000e (DEVa)

Duration: 14.3 s
```

### Conclusions:
Performace remained better than LoS, laying radios was quite fast, but did involve an ammount of backtracking, and already knowing the cave layout helped. 
- The ability to turn off radios will be important to remove under perforiming radios.
- Durability of the current set is not adequate. 
- Medium Fast as a preset allowed much faster traceroutes, and did not seem to perform much worse in caves. 
- Signal thresholds were acceptable down to -15dB, even on Medium Fast. 

## Takeaways 
The radios performed better than expected. They were substantially beyond pure line of site, which anyone that has done surveying will appreciate. Depending on the nature of the blockages to LoS, penetration varies greatly. 

Rockfall seemed to present very little obstacle. One of the legs in Grill involved 5-6m of broken rockfall before a straight passage, and we were still able to get 30+m down the passage after the rockfall. 

Narrow and winding passage was worse for performance, but there must be some reflection, as it was definitely not limited to LoS, being withing a meter or 2 of LoS seemed sufficient.
This obviously needs further investigation, and in different substrates and conditions.

Laying the radios is faster, and less work than laying Michie wire, but there need to be improvements to the user experience in doing so. 

### Improvements for next time
HW
- Need robust cases
- Need string and hanging options to increase placement opportunities
- Hard ON/OFF Switch
- Reflectors & lights to help finding them all when clearing the cave.
- Need more radios, 11 - 15 would be sufficient for the next exercise 
- Need custom firmware, increase max hops to 20 or so, use sw to set to ~10
- Need custom software, remove traceroute cooldown

### Hardware 
6 Radios, 
- 3x RF52 Seeed dev kits
- 2x Heltec v3
- 1x Seeed t1000e

### Firmware
Stock Meshtastic, versions 2.6.11 - 2.7.1

### Software
Meshtastic android 2.6.35 

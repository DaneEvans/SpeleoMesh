# Laying Radios Underground

## Objectives
Lay minimal radios over a given distance.
- ie. maximise the effective range of a given unit in both directions.
This means that the outsides of curves, on the roof before a pitch, or the floor under it.

## Ensuring comms to the last one
- Take note of the previous node's ID as you place it. (Node A)
- Send Node A a DM `ADRT ON` and check that it sends a rangetest packet
    - recieved on channel 0, and the LED (Node B) will change to green
    - If it doesn't send them, try `ADRT DELAY 15` and try again.
- Walk away from Node A, checking the LED on Node B as each message comes in. The LED lights up for 12 seconds, and will then go dark.
- When the LED turns to red, reposition to make it green, and place it (Node B).
- Check the texts for your personal node, and ensure that SNR and RSSI look reasonable.
- Send a DM back to Node A `ADRT OFF`
- repeat for further nodes.

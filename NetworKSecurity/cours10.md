# MAC for wireless LANs

## Why not use CSMA/CD

- can't receive & transmit at the same time, your own transmission is much stronger than the received signal
- radio signals not limited to private medium
- stations not necessarly all in range of each-other

## CSMA with CSMA/CA

- A station ith data to send monitors channel continuously
- when quiet, waith between 0 and 8 short slots
- channel transmits frame if channel still qiet when delay ends
- if, during a delay state, the channek bcomes busy again, the station pauses its delay (resumes when quiet), timer is not reset to favourise stations that have been waiting
- Collision may occur if two stations choose same random delay (stations learn this information through missing frames (missing RR etc.))
  -> both stations initiate another random delay
- Maximum random delay doubles with each succesive collision (binary exponential back-off algorithm)

### Range problem

If a station transmits to another station, due to range, other stations may not know it is transmitting due to wireless' limited range

(A, C in range of B, B and D in range of C)
Hidden station problem: A->B  C  D
If C had data to transmit to B, it would even though it is impossible.
Delay of 2 frames.

Exposed station problem: A<-B  C  D
If C had data to transmit to D, it wouldn't even though it is possible.
Delay of one frame.

# Multiple Access with Collision Avoidance for Wireless (MACAW)

A wishes to transmit to B.

A -> B: RTS with frame size
B -> A: CTS with frame size
A -> B: the actual data
B -> A: ACK
Any computer who hears either the A's RTS or B's CTS will remain quiet until the above transaction.

Collisions less likely due to small frames.
NAV (Network allocation vector) state: station knows another transmission is in progress even if it can't sense it physically.

## Bands and channels

## IEEE 802.11 MAC Frame Format

Name	      |	Size	 |
--------------|----------|
Frame control | 2	 |
Duration      | 2	 |
Address 1 - 3 | 6 * 3	 |
Seq	      | 2   	 |
Address 4     | 6	 |
Data	      | 0 - 2312 |
CRC	      | 4   	 |
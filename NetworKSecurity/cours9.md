# Medium Access Sublayer

- channel allocation problem
- Mac protocols for guided LANs (Ethernet)
- Mac protocols for wrieless LANs (Wi-Fi)

## Channel Allocation Problem

- Several computers, one channel
- Two stations transmitting at the same time this causes a *collision* and the communication is garbled.

## Mac protocols for guided LANs (Ethernet)

### Collision in Continuous timing
- A frame collides if any part of it overlaps another frame
- A frame will only collide if the other is sent within one frame time (t) before or after its start
- Vulnerable time equals twice frame size

### Loading and Throughoutpit

- *Loading* (G) : number of frames offered for transmission per frame time.
  This includes retransmission
- *Throughoutput* (S) : number of frames transmitted suuccesfully / frame time
  Note: S <= 1

### Pure Aloha
- Frames transmitted at arbitrary times
- Each station can detect if a frame it sent has collided
- If collision, sender waits random time and tries again
- `S = Ge^(-2G)` -> optimal at G = 0.5

### Sloted Aloha

- Time is diveid into slots
- Stations may only begin transmission at start of slot
- Reduces period of collision vulnerabillity to 1 frame.
- `S = Ge^(-G)` -> optimal at G = 1.0

### CSMA Protocols

- station monitors channel for other trafic
- 1-persistent CSMA: Monitor channel continuously and transmit when it's quiet
  -> accumulation of waiting stations causes collisions
- Nonpersistent CSMA: Similar to 1-Persistent but if channel busy then wait random time before monitoring again
  -> May wast time with random wait
- P-Persistent CSM: As 1-Persistent but transmit with probablilty p, otherwise defer until next slot

0.01-Persistent has a very high *Throughoutput* but causes variable high latency

### CSMA with collision detection (CSMA/CD)

- detect collisions between frames
- Aborting a crrupted frame quickly saves time and bandwidth
- 1-Persistent CSMA/CD has 3 states: Transmission, Contention and Idle

#### Binary Exponential Back-Off Algorithm

- After collision, time divided into short slots of duration 2 * the maximum propagation delay
- Each waiting stations waits 0 or 1 slot times before retrying (always listen first)
- If new collision double the range of random wait before trying again
- Upper liimt frozen after collisions at 1023 (i.e 1024 possible wait times)
- Transmission will be aborted after 16 collisions

Amount of delay adapts to *Loading*.
Used by 10MB ethernet connections

Frame duration must be greater than twice the maximum propagation delay.
Otherwise, first sender during a collision across two frames will not know collision occured.

### Collision free protocols

- Collision free protocols less effcient when load is light
- Very effective under heavy load
- Garanties transmission (useful in safety-critical applications)

#### Basic bitmap protocool

- Stations reserve a slot
- Contention period contains fixed amount of 1-b slots
- Each station identified by unique number X
- If station X wants to transmit data, it emits 1 in it's slot.
- All stations monitor the contention period, and thus know who's turn it's to transmit

Requires each slot to be as large as a 2 * the propagation delay

### Ethernet (IEEE 802.3)

Uses 1-persistent CSMA/CD with binary exponential back-off.
100 Mps vs 10 Mps -> frame is 10x shorter in 100Mps thus reducing protocol effective latency

#### MAC Frame Format

- Preamble: 7 times 10101010 followed by 10101011
- Destination address: 6 bytes
- Source address: 6 bytes
- Length: 2 bytes, length
- Data: up to 1500 bytes
- Pads: makes frame at least 64 bytes (makes frame long enough), max 46 bytes
- CRC: 4 bytes, cyclic redunduncy check

#### Hub vs Switch

- Hub:
  all computers connected, all data retransmitted to everyone
  - no latency
- Switch:
  examines destination address in each packet header, packet only retransmitted to destination computer's port
  - can allow multiple connection if high quality
  - improves security
  - protocol efficiency inceased due to reduce collision
  - higher latency

### Gigabit Ethernet

- Operates at 1000 Mbps
- Two alt configurations
  - Multidrop: computers connected to a hub
    Uses CSMA/CD but with a larger minimum framesize (512 min bytes)
  - Switched: all links are now point-to-point and full-duplex
    CMSA/CD not needed
  
### Beyond Gigabit Ethernet

- For witched / point-to-point links onlly
- Application include:
  - High speed lan back bone
  - Backplanes for blade servers
  - Alternative to WAN links (avoids packet conversion)
- Cabling options:
  - varied and proprietary
  - copper can be reduced for short distances but require superior cabling
  - Fibre optic only option for longer connections

## Mac protocols for wrieless LANs (Wi-Fi)


# The Data Link Layer

The data link layer turns a raw transmission medium into a reliable communication channel

Operatres between directly linked devices.
- Encapsulate data into rames
- handles detection / correction of errors
- Regulate flow of data
- High-level link management

Service Types:

- Unacknoledged connectionless (CL)
  - Frames transmitted independently
  - reciever may detect errors but no recovery
  - sender has no info about succesful reception

- Acknowledged connection-oriented (CO)
  - A logical connection i established
  - Each frame has unique sequencenumber
  - Receiver acknowledges recetion of frame
  - Sender resends broken and lost frames
  - Protocol guarantees all frames:
    - are delivered succesfully
    - in the correct order
    - without duplicates

# Data Communication techniques

## Framing

Lessages is chopped into frames.
Frame is the same as a packet, but convention has them called packet at higher levels and frame at lower levels of the network stack.

Receiver must:
- identify where a frame begins and ends
- extract and process of each frame

Problems:
- noise may cause errors
- noise may be present in the gap between frames

### Preced frame with frame length
-> ver sensitive to noise

### Flag bytes with byte stuffing
Use a flag to mark begin and end, and use an escpae character

### Flag Bytes with bit stuffing

Save data when many bytes match FLAG or ESC

FLAG has binary code 01111110
If the sender has 5 consectuive 1s in the binary data, it inserts a zero after it (even if the next bit is zero)
01111110 always represents a FLAG at any position and in any context
The receiver can reverse the process.

01001*01111110*1011001110001111000011111~~0~~00000*01111110**01111110*11111~~0~~100000011111~~0~~110000000*01111110*

# Physical Layer Coding Violations

- Use a signal that isn't either 0 or 1, such a signal is called a coding violation

Requires physical layer support. Avoids bit/byte stuffing.


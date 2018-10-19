# Data Link Control Protocols

- Flow control
  - stop-and-wait
  - sliding window
- Error control
  - stop-and-wait ARQ
  - Go-back-N ARQ
  - Selective-reject ARQ

## Flow control

### Stop-and-wait flow control

1. Sender transmits data frame
2. receiiver accepts data frame
3. When the receiver is ready, it sends the receiver ready frame (RR)
4. when sender receives RR, go to 1.

Works with full or half duplex.
Efficiency:
- Lan: stop-and-wait works best over short distances, or when the data rate is low
- Wan: if roundtrip is long, stop-and-wait becomes very inefficient

### Sliding Window Flow Control
Like wait and stop but multiple frames can be transmitted before RR

- Sender can transmit up to W before waiting for RR
- Each data frame contains a sequence number in the range [0, 2^k-1] where k is the size of the sequence number in bits
- Receiver periodecally responds with *RR N* where N  is the seqence number for the next frame it expects, implicitly aknowledging all data up to frame N

Requires full duplex.

## Error control

- positive acknowledgement
- retransmission after timeout
- negative acknowledgement and retransmission (REJ aka NAK)

These mechanisms are known as ARQ.

### Stop-and-Wait AR

Requires sequence numbers.

1. Sender tranmits frame N, strarts a timer and waits for RR
2. If frame N reache receiver without erros reciever responds with RR + 1, duplicated frames are discarded
   **/!\ reciever must still acknowledge duplicate frames /!\**
3. if RR N + 1 reaches reaches sender before timer expires, goto 1. for next frame
4. otherwise goto 1. and try current frame again

Robust mechanism but suffers from same efficiency limitations as basic stop-and-wait.

### Go-back-N ARQ (Basic Version)

- Sender can transmit up to W frames before waiting for RR
- sender starts timer for each frame
- While frames are arriving in correct order the reciever will send RR N periodically
- REceiver discards bad, duplicate, and out-of-sequence frames
- if a frame is aknowledged before timer runs out, the sender cancels the timer
- otherwise the sender goes back to that frame and retransmits the data from that point

Not compatible with out of order frames.
The bigger W, the bigger W. Big W is good when nothing wrong is more efficient but bad in acase of errors.

### Go-Back-N ARQ with Negative Acknowledgment

- if receiver detects out-of-sequence frame it responds immediately by transmitting negative acknowledgment or reject (REJ or NAK) indicating which frame it expects next
- it then waits for that frame
- reciever can retransmit immediatly

Timeout is a catch all safety net (it costs a lot), also required for last (consecutive) frame(s).

### Go-Back-N ARQ (Full version)

When RR is lost, a lot of data has to be retransmitted.

- If sender is missing RR, it can re-ask one with it's own special RR
Since sending special RR requires round-trip to receive e RR, sender can choose between resending frames or sending special RR depending on what is costlier.

#### Maximum window size

= number of sequence numbers available - 1
= 2^k - 1  where k is size of sequence number field in bits

### Selective Reject ARQ

- Similar to go-back-N
  - only those individual frames that time ou or for which selective reject (SREJ) is returned are retransmitted
  - reciver saves ou-of-sequence frames nd reasembles them in corret order when retransitted frames arrive
- Mnimises number of retransmission but requires extra buffer space and more complex control logic

Throughoutput not affected by errors.

#### Maximum window size

Receiver could invalidly think that a frame is missing when it's RR was not received.
This means that all batch of frames should never have overlapping batches.

-> Maximum window size is therefor:
   - number of sequence numbers available / 2
   - 2^(k - 1)

# High-Level Data Link Control (HDLC)

- Has been adpted into new technologies:
  - PPP (Point to Point PRotocol)
  - LLC (Logical Link Control)
- Supports:
  - Point-topoint and multidrop (LLC handles multipoint too)
  - Half duplex and full duplex links
  - Connectopn oriented and connectionless service

## Frame Structure

FLAG: 8 bits
Addres:  8 bits, extendable (not needed for point-to-point links),
Control: 8 or 16 bits  // type of frame
Data: 0 or more bytes
FCS: 8 or 16 bits
FLAG: 8 bits

3 categiry information, supervisory and unumbered

## Information Frames (I-frames)

2 sequence numbers:
- N(S) sequence number of this I-frame defined by station that sent this frame
- N(R) sequence number of next I-frame expected from other station, acknowledging I-frames received byt station that sent this frame

## Supervisory Frames

- Receive Ready RR
- Rject
- Select Reject
- RNR is similar but tells sender not to ransmit any more l-frames until further notice.
  Receiver will transmit RR when ready

RNR is used to avoid timeout.
Control field contains one sequence number

## numbered frames (U-frames)

- Set Asunchonous Balanced Mode (SABM)
  request to establish data link connection
- Disconnect (DISC)
- Unnumbered Information (UI)
- Unumbered Acknowledgement (UA)